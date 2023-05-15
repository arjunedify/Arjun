**LMS Deployment on kubernetes using minikube in single Virtual Machine**


 ![](RackMultipart20230515-1-g0fvh5_html_ed0c4c9ec2518645.png)

##

 **Installation**


##


 Docker
 minikube
 kubectl


 ports to open

 22
 80
 32000-32767




Yamls file Required backend and database

 ![](RackMultipart20230515-1-g0fvh5_html_cc78386e3414d328.png)

Images required and push the image to docker hub

**1. Backend image**

 $docker build -t k8s-backend .


 ![](RackMultipart20230515-1-g0fvh5_html_a3ad352fc61ae076.png)


**2. Push the image to docker hub**

 docker login

 and docker push.

![](RackMultipart20230515-1-g0fvh5_html_bca537e019f17c59.png)

**3. Create a persistant volume**

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

component: postgres

spec:

storageClassName: manual

capacity:

storage: 1Gi # Sets PV Volume

accessModes:

- ReadWriteMany

hostPath:

path: "/mtd/data" # Sets the volume's path

![](RackMultipart20230515-1-g0fvh5_html_32c6ec56d182d6c.png)
 Commands to create :
kubectl create –f database-persistent-volume.yaml


**4. Deploy postgres deployment file**


 ubuntu@ip-172-31-16-132:~/lms-public/api$ cat postgres-deployment.yaml

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

![](RackMultipart20230515-1-g0fvh5_html_f834df9185887c4d.png)

Commands to create:

$ kubectl create –f postgres-deployment.yaml

**5. Create service for postgres service**

 ubuntu@ip-172-31-16-132:~/lms-public/api$ cat postgres-cluster-ip-service.yaml

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


 ![](RackMultipart20230515-1-g0fvh5_html_d6296ab2746fcc8b.png)


 commands:

 $ kubectl create –f postgres-cluster-ip-service.yaml

**6 . Create Backend deployment file**

 ubuntu@ip-172-31-16-132:~/lms-public/api$ cat api-deployment.yaml

apiVersion: apps/v1

kind: Deployment

metadata:

name: api-deployment

spec:

replicas: 1

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

image: mubeen507/backend

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

 ![](RackMultipart20230515-1-g0fvh5_html_21ebe7a2c242d354.png)
 commands:

 kubectl create –f api-deployment.yaml

**7. Create the service for backend**

ubuntu@ip-172-31-16-132:~/lms-public/api$ cat api-load-balancer-service.yaml

apiVersion: v1

kind: Service

metadata:

name: api-service

spec:

selector:

component: api

ports:

- protocol: TCP

port: 3000

targetPort: 3000

type: NodePort


 ![](RackMultipart20230515-1-g0fvh5_html_cee08e8ef2560b3a.png)

 Command :
 kubectl create –f api-load-balancer-service.yaml

**Step 8. Verify(postgres and backend ) with commands**

##


 Testing pods and services working or not properly


 Commands

 kubectl get all


 ![](RackMultipart20230515-1-g0fvh5_html_ebac083eaa634a40.png)


 Get the backend url
 Command :
 minikube service api-service –url


 ![](RackMultipart20230515-1-g0fvh5_html_1d77074a0c1937dc.png)


Open the port in security group from 30000 to 32767

 check internally with above url

 curl [http://192.168.49.2:31845](http://192.168.49.2:31845/)

 ![](RackMultipart20230515-1-g0fvh5_html_9352b8e3d9337652.png)

 Now use port forward command to access service externally
 by using the commands

 $ kubectl port-forward --address 0.0.0.0 service/api-service 31845:3000

 ![](RackMultipart20230515-1-g0fvh5_html_8e29847bd505e722.png)

 Now open externalip:serviceport from browser to verify


http:// 54.183.115.220:31845

 ![](RackMultipart20230515-1-g0fvh5_html_826681c80a793e3d.png)

# **Frontend**

## :


![Shape1](RackMultipart20230515-1-g0fvh5_html_a892e8b0c0b96247.gif) **9. Deploying frontend**

##
 Before that update the .env file

 update the .env file of frontend that is web app


 ![](RackMultipart20230515-1-g0fvh5_html_67a84f32bd8ee101.png)
##

 with url where our currenly backend is running on

 as shown in pic

![](RackMultipart20230515-1-g0fvh5_html_826681c80a793e3d.png)

Building the frontend image first

$docker build –t mubeen507/frontend-lms .

 ![](RackMultipart20230515-1-g0fvh5_html_f8ae598d4aa40b57.png)
 and push hub docker
 ![](RackMultipart20230515-1-g0fvh5_html_66bc6ded8e178e83.png)
 Docker images

 ![](RackMultipart20230515-1-g0fvh5_html_fb10877fb3e0de09.png)

 ubuntu@ip-172-31-16-132:~/lms-public/webapp$ sudo vi frontend-deployment.yaml

ubuntu@ip-172-31-16-132:~/lms-public/webapp$ cat frontend-deployment.yaml

apiVersion: apps/v1

kind: Deployment

metadata:

name: frontend-deployment

spec:

replicas:

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

image: mubeen507/frontend-lms

imagePullPolicy: Always

ports:

- containerPort: 80

env:

- name: MODE

value: production

- name: VITE\_API\_URL

value: api-load-balancer-service

![](RackMultipart20230515-1-g0fvh5_html_af6e7801b241ef96.png)


 Commands

 kubectl create –f frontend-deployment.yaml

**10 . create service for frontend**

 apiVersion: v1

kind: Service

metadata:

name: frontend-nodeport-service

spec:

type: NodePort

ports:

- port: 80

targetPort: 80

selector:

component: frontend

![](RackMultipart20230515-1-g0fvh5_html_18627c3a2140bb4.png)

commands:


 $ minikube service frontend-nodeport-service --url
 ![](RackMultipart20230515-1-g0fvh5_html_8444dd3fc79bc3ea.png)
 Exposing frontend to outside world

 command :

 kubectl port-forward --address 0.0.0.0 service/frontend-nodeport-service 30633:80

 ![](RackMultipart20230515-1-g0fvh5_html_ee7aec46817dae06.png)

public ip address of minikube instance : nodeport number

 http://54.183.115.220:30633

 ![](RackMultipart20230515-1-g0fvh5_html_5b2666463d7b3214.png)

9 | Page
