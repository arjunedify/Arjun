**ELASTIC KUBERNETES SERVICE**

**Instance type-**** t2 medium**

**Os-** ubuntu-20.04

**Security group**  -443,5432,80,8080

**Install eksctl:**

**curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl\_$(uname -s)\_amd64.tar.gz" | tar xz -C /tmp**

**sudo mv /tmp/eksctl /usr/local/bin**

**eksctl version**

**Install kubectl:**

**curl -O** [**https://s3.us-west-2.amazonaws.com/amazon-eks/1.24.7/2022-10-31/bin/linux/amd64/kubectl**](https://s3.us-west-2.amazonaws.com/amazon-eks/1.24.7/2022-10-31/bin/linux/amd64/kubectl)

**curl -O** [**https://s3.us-west-2.amazonaws.com/amazon-eks/1.24.7/2022-10-31/bin/linux/amd64/kubectl.sha256**](https://s3.us-west-2.amazonaws.com/amazon-eks/1.24.7/2022-10-31/bin/linux/amd64/kubectl.sha256)

**openssl sha1 -sha256 kubectl**

**chmod +x ./kubectl**

**sudo mv kubectl /usr/local/bin**

**mkdir -p $HOME/bin && cp ./kubectl $HOME/bin/kubectl && export PATH=$PATH:$HOME/bin**

**echo 'export PATH=$PATH:$HOME/bin' \>\> ~/.bashrc**

**kubectl version --short –client**

**Install aws cli:**

**curl "https://awscli.amazonaws.com/awscli-exe-linux-x86\_64.zip" -o "awscliv2.zip"**

**sudo apt -y install unzip**

**unzip awscliv2.zip**

**sudo ./aws/install**

**Install aws-iam-authenticator:**

**curl -Lo aws-iam-authenticator** [**https://github.com/kubernetes-sigs/aws-iam-authenticator/releases/download/v0.5.9/aws-iam-authenticator\_0.5.9\_linux\_amd64**](https://github.com/kubernetes-sigs/aws-iam-authenticator/releases/download/v0.5.9/aws-iam-authenticator_0.5.9_linux_amd64)

**chmod +x ./aws-iam-authenticator**

**mkdir -p $HOME/bin && cp ./aws-iam-authenticator $HOME/bin/aws-iam-authenticator && export PATH=$PATH:$HOME/bin**

**echo 'export PATH=$PATH:$HOME/bin' \>\> ~/.bashrc**

**aws-iam-authenticator help**

**Create IAM role:**

The eks-role should have the following access

[AmazonEC2FullAccess](https://us-east-1.console.aws.amazon.com/iam/home#/policies/arn:aws:iam::aws:policy/AmazonEC2FullAccess)

[AdministratorAccess](https://us-east-1.console.aws.amazon.com/iam/home#/policies/arn:aws:iam::aws:policy/AdministratorAccess)

[AmazonVPCFullAccess](https://us-east-1.console.aws.amazon.com/iam/home#/policies/arn:aws:iam::aws:policy/AmazonVPCFullAccess)

[AWSCloudFormationFullAccess](https://us-east-1.console.aws.amazon.com/iam/home#/policies/arn:aws:iam::aws:policy/AWSCloudFormationFullAccess)

![](RackMultipart20230519-1-3xue4s_html_e32d1a56e4df6768.png)

- Attach the IAM role to the instance

![](RackMultipart20230519-1-3xue4s_html_7a82452a585a4d04.png)

**Create the eks cluster:**

**eksctl create cluster --name test-cluster --version 1.24 --region us-west-2 --nodegroup-name linux-node --node-type t2.medium --nodes 2**

![](RackMultipart20230519-1-3xue4s_html_9aa7344e716dbd03.png)

Now clone the code into the workstation

- sudo git clone -b EKS -b [https://github.com/yellaiahgithub/lms-public.git](https://github.com/yellaiahgithub/lms-public.git)

- ![](RackMultipart20230519-1-3xue4s_html_ba08bd92c1cd0999.png)

- Change the directory to lms-public/k8s

![](RackMultipart20230519-1-3xue4s_html_e654291d74444687.png)

[**api-deployment.yaml**](https://github.com/yellaiahgithub/lms-public/blob/EKS/k8s/api-deployment.yaml)

apiVersion: apps/v1

kind: Deployment

metadata:

name: api-deployment

spec:

replicas: 2

selector:

matchLabels:

component: api

template:

metadata:

labels:

component: api

spec:

containers:

- name: api

image: yellaiahdocker/backend-k8s

imagePullPolicy: Always

ports:

- containerPort: 3000

env:

- name: PORT

value: "3000"

- name: MODE

value: production

- name: DB\_HOST

value: postgres-cluster-ip-service

- name: DB\_PORT

value: "5432"

- name: DB\_USER

value: postgres

- name: DB\_NAME

value: postgres

- name: DB\_PASSWORD

value: password

## **api-load-balancer-service.yaml**

apiVersion: v1

kind: Service

metadata:

name: api-load-balancer-service

spec:

type: LoadBalancer

ports:

- port: 3000

targetPort: 3000

selector:

component: api

## **database-persistent-volume-claim.yaml**

apiVersion: v1

kind: PersistentVolumeClaim

metadata:

name: postgres-pv-claim

labels:

component: postgres

spec:

storageClassName: manual

accessModes:

- ReadWriteOnce

resources:

requests:

storage: 1Gi

---

kind: PersistentVolume # Create a PV

apiVersion: v1

metadata:

name: postgres-pv-volume # Sets PV's name

labels:

type: local # Sets PV's type to local

component: postgres

spec:

storageClassName: manual

capacity:

storage: 1Gi # Sets PV Volume

accessModes:

- ReadWriteMany

hostPath:

path: "/mtd/data" # Sets the volume's path

## **postgres-cluster-ip-service.yaml**

apiVersion: v1

kind: Service

metadata:

name: postgres-cluster-ip-service

spec:

type: ClusterIP

selector:

component: postgres

ports:

- port: 5432

targetPort: 5432

## **postgres-deployment.yaml**

apiVersion: apps/v1

kind: Deployment

metadata:

name: postgres-deployment

spec:

replicas: 1

selector:

matchLabels:

component: postgres

template:

metadata:

labels:

component: postgres

spec:

# volume configuration for the pod

volumes:

- name: postgres-storage

persistentVolumeClaim:

containers:

- name: postgres

image: postgres

ports:

- containerPort: 5432

# volume mounting configuration for the container

volumeMounts:

- name: postgres-storage

mountPath: /var/lib/postgresql/data

subPath: postgres

env:

- name: POSTGRES\_PASSWORD

value: password

- Run the following commands for deployment

kubectl create -f database-persistent-volume-claim.yaml

kubectl create -f postgres-deployment.yaml

kubectl create -f postgres-cluster-ip-service.yaml

kubectl create -f api-deployment.yaml

kubectl create -f api-load-balancer-service.yaml

- Now check the pods and services

Kubectl get all

![](RackMultipart20230519-1-3xue4s_html_9215438c77e95d38.png)

Now check the backend address

http://[a389da76f9f8943c2827c6b071aaf444-885465126.us-west-2.elb.amazonaws.com:3000](http://a389da76f9f8943c2827c6b071aaf444-885465126.us-west-2.elb.amazonaws.com:3000/)

![](RackMultipart20230519-1-3xue4s_html_1faed1793bcb8c6.png)

- Now copy the backend url and paste in lms-public/webapp/.env file

![](RackMultipart20230519-1-3xue4s_html_dcc87bb6ae96f725.png)

- Now build the frontend docker image with the above backend\_url and push into dockerhub account ,Then from dockerhub account the frontend-deployment file will call the frontend image.

![](RackMultipart20230519-1-3xue4s_html_ff437e00cdfa614.png)

## **frontend-deployment.yaml**

apiVersion: apps/v1

kind: Deployment

metadata:

name: frontend-deployment

spec:

replicas: 2

selector:

matchLabels:

component: frontend

template:

metadata:

labels:

component: frontend

spec:

containers:

- name: frontend

image: yellaiahdocker/frontend-working

imagePullPolicy: Always

ports:

- containerPort: 80

env:

- name: MODE

value: production

- name: VITE\_API\_URL

value: api-load-balancer-service

## frontend-load-balancer-service.yaml

apiVersion: v1

kind: Service

metadata:

name: frontend-load-balancer-service

spec:

type: LoadBalancer

ports:

- port: 80

targetPort: 80

selector:

component: frontend

- Now the following commands for frontend deployment in EKS cluster

kubectl create -f frontend-deployment.yaml

kubectl create -f frontend-load-balancer-service.yaml

- Now check frontend pods and service

Kubectl get all

![](RackMultipart20230519-1-3xue4s_html_3b82223e07c928b5.png)

- Now check the deployment service url

http://[a30114a1eaf5945de95285208d84d1d3-677222305.us-west-2.elb.amazonaws.com](http://a30114a1eaf5945de95285208d84d1d3-677222305.us-west-2.elb.amazonaws.com/)

![](RackMultipart20230519-1-3xue4s_html_fd506c4c9f38286c.png)
