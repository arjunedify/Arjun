_CI /CD FOR LMS REACT APPLICATION_

Architecture Diagram

 ![image](https://github.com/arjunedify/Arjun/assets/132984407/f52cdf93-c5ac-4707-8e64-bd1b3c37e5f8)

 Repository url

[https://github.com/mubeen507/lms-public.git](https://github.com/mubeen507/lms-public.git)

Task to Dockerize the LMS react App Project

Prerequisites

WGET

GIT

JAVA 11

JENKINS

DOCKER

# _Brief review about project_

1.
### _We need to two instance one for master (jenkins) and Slave (docker container)_
2.
# _Docker installed in slave Server(ubuntu)_
3.
# _Jenkins as Master in server (ubuntu)_
4.
# _In Docker slave server install docker, java11 and create a docker network with name lmsnetwork_
5.
# _In Jenkins Master server configure node as docker server as slave_
6.
# _In Jenkins server create pipeline backend pipeline and test backend it should be up and running._
7.
# _Once the backend is running Update the backend url in frontend in frontend /webapp .env file._
8.
# _Now create a Frontend pipeline ._

![image](https://github.com/arjunedify/Arjun/assets/132984407/5d12bccb-87b9-43e2-a7f4-677f39eb48cc)

Slave Server is our docker server

Step 1: Configuration of Docker server

$ sudo app

- **Instance type-**** t2 medium**
- **Os-** ubuntu-20.04
- **Security ports to be opend**
443, 5432(for database) ,80 , 8080,8000

- Install docker
[**www.get.docker.com**](http://www.get.docker.com/)

Installation commands

url -f
```
 curl -fsSL https://get.docker.com -o get-docker.sh
```
```
sh get-docker.sh
```
Starting Docker Service
```
 sudo systemctl start docker
```
Enabling Docker Service
```
 sudo systemctl enable docker
```
(adding centos user to docker group)
```
 sudo usermod -aG docker ubuntu
```
```
 newgrp docker
```
# **Creating docker network**

commad to create a docker network
```
docker network create -d bridge lmsnetwork
```
![image](https://github.com/arjunedify/Arjun/assets/132984407/e21d0478-becf-4cad-a865-4ee0ce9a1f1f)

**Goto another instance that MASTER (jenkins server)**

Installing Jenkins server

[www.jenkins.io](http://www.jenkins.io/)
```
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo tee\

/usr/share/keyrings/jenkins-keyring.asc **\>** /dev/null
```
```
echo deb **[**signed-by **=** /usr/share/keyrings/jenkins-keyring.asc] \

https://pkg.jenkins.io/debian-stable binary/ | sudo tee\

/etc/apt/sources.list.d/jenkins.list **\>** /dev/null
```
```
sudo apt-get update
```
```
sudo apt-get install jenkins
```
login to Jenkins server and install suggested plugins

![image](https://github.com/arjunedify/Arjun/assets/132984407/ed06f646-b424-4332-a822-4883b0ce247b)

Now configuration Jenkins Master slave configuration

![image](https://github.com/arjunedify/Arjun/assets/132984407/d15d677d-e745-4026-b3f4-642db44cdffd)

![image](https://github.com/arjunedify/Arjun/assets/132984407/509f196d-d5d3-49e1-bf8c-2f26ab9cd327)

**Configuring Master slave in Jenkins**

![image](https://github.com/arjunedify/Arjun/assets/132984407/14ace91a-923e-40ba-86c0-8f3a33ad276c)

![image](https://github.com/arjunedify/Arjun/assets/132984407/d8bcca4a-4e5b-4a1b-8d42-007f80796b59)

![image](https://github.com/arjunedify/Arjun/assets/132984407/2b733b41-9fe0-42d7-844f-641aa20790a6)

Now add user

![image](https://github.com/arjunedify/Arjun/assets/132984407/dfe11ac0-dbc3-478e-9af0-091f52617575)

![image](https://github.com/arjunedify/Arjun/assets/132984407/d4c83c0d-6a1e-4a3d-8986-e5f8f6ef82de)

![image](https://github.com/arjunedify/Arjun/assets/132984407/9ec86b12-0690-4d67-982a-4230ed5e6de0)

Note : In slave install Java 11 as Jenkins required
```
sudo apt install openjdk-11-jre
```
![image](https://github.com/arjunedify/Arjun/assets/132984407/df15243e-de3d-4549-8771-73fa6435abd4)

Now Master slave configuration is completed

Now create a Job (pipeline job) in Jenkins

![image](https://github.com/arjunedify/Arjun/assets/132984407/c4c9dc86-9554-4ef8-a2d0-a4c419b1ec03)

Goto Manage credentials

Add your dockerhub user credentials in jekins

![image](https://github.com/arjunedify/Arjun/assets/132984407/75af2d38-6109-43e0-a458-95e72f5e1874)

Done with configuration of master and slave

Now configuring Backend pipeline

 Now create a jenkins file that is [mubeen507](https://github.com/mubeen507)/[**lmsreactproject**](https://github.com/mubeen507/lmsreactproject) **/** api/Jenkinsfile-docker-backend in your git hub repository
```
Jenkins file

pipeline {

agent{

label 'docker'

}

environment {

DOCKERHUB\_CREDENTIALS = credentials('dockerusermubeen')

registry = "mubeen507/backend-lms"

registryCredential = 'dockerusermubeen'

dockerImage = ''

}

stages {

stage('Building the docker image') {

steps {

sh 'cd api && docker build -t mubeen507/backend-lms .'

}

}

stage('Logging into dockerhub account') {

steps {

sh 'echo $DOCKERHUB\_CREDENTIALS\_PSW | docker login -u $DOCKERHUB\_CREDENTIALS\_USR --password-stdin'

}

}

stage('pushing the docker image into dockerhub') {

steps {

sh 'docker push mubeen507/backend-lms'

}

}

stage('Remove old docker images') {

steps {

sh 'docker rmi -f mubeen507/backend-lms'

}

}

stage('creating database container') {

steps {

sh 'docker container rm --force lmsdb'

sh 'docker run -d -p 5432:5432 --network lmsnetwork -e POSTGRES\_PASSWORD=password --name lmsdb postgres'

}

}

stage('Running the docker container') {

steps {

sh 'docker container rm --force backend'

sh 'docker run -d -p 8080:8080 --network lmsnetwork -e DATABASE\_URL=postgresql://postgres:password@lmsdb:5432/postgres --name backend -e PORT=8080 -e MODE=local mubeen507/backend-lms'

}

}

}

}
```

Configure docker hub credentials

![image](https://github.com/arjunedify/Arjun/assets/132984407/afcfa1d4-575a-48d1-bc10-6edd61ca1f1b)

Now configuring git

![image](https://github.com/arjunedify/Arjun/assets/132984407/2eb255de-b735-46d1-b899-3ac233034a6f)

Build the Backend pipeline then update he url of backend in frontend
 at /webapp/.env file

![image](https://github.com/arjunedify/Arjun/assets/132984407/7dd8b933-88a1-4253-9266-759181753237)

Now test the backend server

![image](https://github.com/arjunedify/Arjun/assets/132984407/4a044735-6ddf-4890-9979-86bb0338af9f)

Backend is up and running Now

End of backend configuration

**Deploying front End**

Now Create FrontEnd pipeline in jenkins after updating of backend url in webapp .

Note : to build frontend our backend should be up and running .

![image](https://github.com/arjunedify/Arjun/assets/132984407/383f3444-3ba1-4489-a5f8-8c767e56e155)

Now add jenkins files at in frontend /webapp/nameof jenkinsfile
```
Jenkinsfile for frontend
pipeline {

agent {

label 'docker'

}

environment {

DOCKERHUB\_CREDENTIALS = credentials('dockerusermubeen')

registry = "mubeen507/frontend-lms"

registryCredential = 'dockerhub'

}

stages {

stage('Building the docker image') {

steps {

sh 'cd webapp && docker build -t mubeen507/frontend-lms .'

}

}

stage('Logging into dockerhub account') {

steps {

sh 'echo $DOCKERHUB\_CREDENTIALS\_PSW | docker login -u $DOCKERHUB\_CREDENTIALS\_USR --password-stdin'

}

}

stage('pushing the docker image into dockerhub') {

steps {

sh 'docker push mubeen507/frontend-lms'

}

}

stage('Remove old docker images') {

steps {

sh 'docker rmi -f mubeen507/frontend-lms'

}

}

stage('Running the docker container') {

steps {

sh 'docker container rm --force fe'

sh 'docker run -dt -p 8000:80 --name fe mubeen507/frontend-lms'

}

}

}

}
```
Update user credential of docker user (example dockeruser )jenkinsfile

![image](https://github.com/arjunedify/Arjun/assets/132984407/b12dbad0-5a4c-4074-a138-e6cfbc564130)

Now Build frontend pipeline

And set your dockerhubusername/imagename


Note : Update URL of Backend in .env of webapp (as webapp is you frontend) before building application.

For Example backend is running on 54.183.228:8080/api

Note : update the Backend url in FrontEnd webapp .env

Creating of frontend pipeline

![image](https://github.com/arjunedify/Arjun/assets/132984407/340bd71d-1168-4a21-8207-ccd1cfe32a1a)

Provide the git repository

![image](https://github.com/arjunedify/Arjun/assets/132984407/e4080226-b6fc-43e8-9c06-bb05a193dfc9)

Provide the jenkinsfile location

![image](https://github.com/arjunedify/Arjun/assets/132984407/c52dc54a-de0e-4b78-b759-eb6efafed874)

![image](https://github.com/arjunedify/Arjun/assets/132984407/ceecad1d-a186-4f1e-8e19-b869500c5242)

![image](https://github.com/arjunedify/Arjun/assets/132984407/29fcbd8b-11be-4705-be67-37e33d912761)

[Type here]
