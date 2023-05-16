**LMS Deployment on kubernetes using minikube in single Virtual Machine**

![image](https://github.com/arjunedify/Arjun/assets/132984407/57dc01f2-9472-46dc-beb8-cf5d1dc2e20c)

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

 ![image](https://github.com/arjunedify/Arjun/assets/132984407/154a0831-f94c-441f-9169-6e8cdda86e60)

Images required and push the image to docker hub

**1. Backend image**

 $docker build -t k8s-backend .

![image](https://github.com/arjunedify/Arjun/assets/132984407/d3bec4fa-f59a-4361-b6f7-c8379964628c)

**2. Push the image to docker hub**

 docker login

 and docker push.

![image](https://github.com/arjunedify/Arjun/assets/132984407/cc0102b0-db5e-4e7a-8df9-d9c2890dfeec)

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

![image](https://github.com/arjunedify/Arjun/assets/132984407/6475c002-47f4-454a-af5b-70fbcbf579bf)
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
![image](https://github.com/arjunedify/Arjun/assets/132984407/696a7da3-8922-4f8b-a99c-d9ab2ecf3d26)


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

 ![image](https://github.com/arjunedify/Arjun/assets/132984407/6f57269d-c8e9-47e3-91fe-943dc2f0686a)

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

 ![image](https://github.com/arjunedify/Arjun/assets/132984407/615fe9e6-9598-4300-b89b-10a9c1db4b3f)

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

![image](https://github.com/arjunedify/Arjun/assets/132984407/d9ab31e9-5108-4bad-bf9b-fc5554544b3c)

 Command :
 kubectl create –f api-load-balancer-service.yaml

**Step 8. Verify(postgres and backend ) with commands**

##


 Testing pods and services working or not properly


 Commands

 kubectl get all

 ![image](https://github.com/arjunedify/Arjun/assets/132984407/be6dcbf3-58ae-48f6-b5c2-bdf5e45e429f)


 Get the backend url
 Command :
 minikube service api-service –url

![image](https://github.com/arjunedify/Arjun/assets/132984407/1087f89f-15a1-4d27-ac86-3907eea1e963)


Open the port in security group from 30000 to 32767

 check internally with above url

 curl [http://192.168.49.2:31845](http://192.168.49.2:31845/)

 ![image](https://github.com/arjunedify/Arjun/assets/132984407/123fac48-f8ec-4659-a3d6-c5c7b0b88535)

 Now use port forward command to access service externally
 by using the commands

 $ kubectl port-forward --address 0.0.0.0 service/api-service 31845:3000

 ![image](https://github.com/arjunedify/Arjun/assets/132984407/f4315efa-eb87-44f0-86c8-d95bba95a562)

 Now open externalip:serviceport from browser to verify


http:// 54.183.115.220:31845

![image](https://github.com/arjunedify/Arjun/assets/132984407/5bf1a9d6-e44f-42e1-b667-b37aae9de1da)

# **Frontend**

## :

![image](https://github.com/arjunedify/Arjun/assets/132984407/b831a1c3-200e-47c8-afd8-f4e769e2abeb)
**9. Deploying frontend**

##
 Before that update the .env file

 update the .env file of frontend that is web app

![image](https://github.com/arjunedify/Arjun/assets/132984407/7d8323e1-8f71-4c07-8d80-515a2535494a)

##

 with url where our currenly backend is running on

 as shown in pic

![image](https://github.com/arjunedify/Arjun/assets/132984407/88560da1-a252-4b75-b580-3eb0b24e1e40)

Building the frontend image first

$docker build –t mubeen507/frontend-lms .

 ![image](https://github.com/arjunedify/Arjun/assets/132984407/e91ccb17-22aa-41af-8960-87ded1623241)

 and push hub docker
![image](https://github.com/arjunedify/Arjun/assets/132984407/cafdabec-ff09-4737-8d69-bf5093461519)

 Docker images

 ![image](https://github.com/arjunedify/Arjun/assets/132984407/bea8c87a-3d70-4871-9a47-b6bb3592cad3)

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

![image](https://github.com/arjunedify/Arjun/assets/132984407/4ceba6e9-86cf-4f7e-bd5c-abe201ac8995)


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

![image](https://github.com/arjunedify/Arjun/assets/132984407/e90c9596-0516-4f47-b8e4-8328064bcd85)

commands:


 $ minikube service frontend-nodeport-service --url
 ![image](https://github.com/arjunedify/Arjun/assets/132984407/bf1151aa-16cf-49ee-87a4-bfdd003eb502)
 Exposing frontend to outside world

 command :

 kubectl port-forward --address 0.0.0.0 service/frontend-nodeport-service 30633:80

 ![image](https://github.com/arjunedify/Arjun/assets/132984407/4e1858b7-4b8d-492b-b16b-6f328bb31d46)

public ip address of minikube instance : nodeport number

 http://54.183.115.220:30633

![image](https://github.com/arjunedify/Arjun/assets/132984407/c20e2041-ed24-4243-8049-8b4a4817db94)

9 | Page
