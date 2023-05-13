CI /CD FOR LMS REACT APPLICATION_

Architecture Diagram

 ![](RackMultipart20230513-1-688ly4_html_9d9b6b51480f8859.png)

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
# _We need to two instance one for master (jenkins) and Slave (docker container)_
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

![](RackMultipart20230513-1-688ly4_html_a03cd1d24c79687f.png)

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

# curl -fsSL https://get.docker.com -o get-docker.sh

# sh get-docker.sh

Starting Docker Service

# sudo systemctl start docker

Enabling Docker Service

# sudo systemctl enable docker

(adding centos user to docker group)

# sudo usermod -aG docker ubuntu

# newgrp docker

# **Creating docker network**

commad to create a docker network

# docker network create -d bridge lmsnetwork

![](RackMultipart20230513-1-688ly4_html_365df7ebcad95cee.png)

**Goto another instance that MASTER (jenkins server)**

Installing Jenkins server

[www.jenkins.io](http://www.jenkins.io/)

curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo tee\

/usr/share/keyrings/jenkins-keyring.asc **\>** /dev/null

echo deb **[**signed-by **=** /usr/share/keyrings/jenkins-keyring.asc] \

https://pkg.jenkins.io/debian-stable binary/ | sudo tee\

/etc/apt/sources.list.d/jenkins.list **\>** /dev/null

sudo apt-get update

sudo apt-get install jenkins

login to Jenkins server and install suggested plugins

![](RackMultipart20230513-1-688ly4_html_56a4d81f65473553.png)

Now configuration Jenkins Master slave configuration

![](RackMultipart20230513-1-688ly4_html_7889b4b10209919a.png)

![](RackMultipart20230513-1-688ly4_html_3e30c4e31ba564a5.png)

**Configuring Master slave in Jenkins**

![](RackMultipart20230513-1-688ly4_html_43912879f7132fa4.png)

![](RackMultipart20230513-1-688ly4_html_42ce984f6b71a397.png)

![](RackMultipart20230513-1-688ly4_html_c268740ac26b0bf8.png)

Now add user

![](RackMultipart20230513-1-688ly4_html_c90d378d5823f7f7.png)

![](RackMultipart20230513-1-688ly4_html_90cf0fddd0f21ed6.png)

![](RackMultipart20230513-1-688ly4_html_c1c252f6cdd2bd21.png)

Note : In slave install Java 11 as Jenkins required

sudo apt install openjdk-11-jre

![](RackMultipart20230513-1-688ly4_html_d3ee9caad5d11e93.png)

Now Master slave configuration is completed

Now create a Job (pipeline job) in Jenkins

![](RackMultipart20230513-1-688ly4_html_78974d1282c44d5b.png)

Goto Manage credentials

Add your dockerhub user credentials in jekins

![](RackMultipart20230513-1-688ly4_html_6bf42b6d608b355f.png)

Done with configuration of master and slave

Now configuring Backend pipeline

 Now create a jenkins file that is [mubeen507](https://github.com/mubeen507)/[**lmsreactproject**](https://github.com/mubeen507/lmsreactproject) **/** api/Jenkinsfile-docker-backend in your git hub repository

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

Configure docker hub credentials

![](RackMultipart20230513-1-688ly4_html_342a5a71b482055f.png)

Now configuring git

![](RackMultipart20230513-1-688ly4_html_6c8991cb5c450380.png)

Build the Backend pipeline then update he url of backend in frontend
 at /webapp/.env file

![](RackMultipart20230513-1-688ly4_html_cd52e97fe6fdb98f.png)

Now test the backend server

![](RackMultipart20230513-1-688ly4_html_7a0e99da1572363f.png)

Backend is up and running Now

End of backend configuration

**Deploying front End**

Now Create FrontEnd pipeline in jenkins after updating of backend url in webapp .

Note : to build frontend our backend should be up and running .

![](RackMultipart20230513-1-688ly4_html_c70faa07f2a35762.png)

Now add jenkins files at in frontend /webapp/nameof jenkinsfile

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

Update user credential of docker user (example dockeruser )jenkinsfile

![](RackMultipart20230513-1-688ly4_html_49541b6db8ee9e4f.png)

Now Build frontend pipeline

And set your dockerhubusername/imagename


Note : Update URL of Backend in .env of webapp (as webapp is you frontend) before building application.

For Example backend is running on 54.183.228:8080/api

Note : update the Backend url in FrontEnd webapp .env

Creating of frontend pipeline

![](RackMultipart20230513-1-688ly4_html_79618c81d6684059.png)

Provide the git repository

![](RackMultipart20230513-1-688ly4_html_d64986cc3fd4a7fc.png)

Provide the jenkinsfile location

![](RackMultipart20230513-1-688ly4_html_184019e9fa8a9eb2.png)

![](RackMultipart20230513-1-688ly4_html_edef3663090d646c.png)

![](RackMultipart20230513-1-688ly4_html_a84210776d2f438a.png)

[Type here]
