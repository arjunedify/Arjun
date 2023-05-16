# Project Pipeline

**Requirements**

Operating System Centos 7:

From AWS marketplace

Git Repository URL:

[https://github.com/mubeen507/project.git](https://github.com/mubeen507/project.git)

Jenkins Download URL:

[https://www.jenkins.io/doc/book/installing/linux/#red-hat-centos](https://www.jenkins.io/doc/book/installing/linux/#red-hat-centos)

**Jenkins installation Steps**

![image](https://github.com/arjunedify/Arjun/assets/132984407/473c5762-32e5-4ce7-8c00-33a88952079a)


sudo yum install wget -y

sudo wget -O /etc/yum.repos.d/jenkins.repo \

https://pkg.jenkins.io/redhat-stable/jenkins.repo

sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key

sudo yum upgrade

_# Add required dependencies for the jenkins package_

sudo yum install java-11-openjdk

sudo yum install jenkins

sudo systemctl daemon-reload

sudo systemctl start Jenkins

sudo systemctl enable Jenkins

sudo netstat -ntpl

java - -version

![image](https://github.com/arjunedify/Arjun/assets/132984407/e87a2612-d5c1-4a17-b5db-a9622d0aeaf3)

Install suggested Plugins

**Install git:**

sudo yum install git -y

**Installing Maven**

[https://maven.apache.org/download.cgi](https://maven.apache.org/download.cgi)

![image](https://github.com/arjunedify/Arjun/assets/132984407/38dcdcb2-def8-489a-a53c-8c489d646843)

**Copy the url**

wget https://dlcdn.apache.org/maven/maven-3/3.9.1/binaries/apache-maven-3.9.1-bin.tar.gz

ls

tar -xf apache-maven-3.9.1-bin.tar.gz

cp -rf apache-maven-3.9.1 maven

now move the maven to usr share directory

mv maven /usr/share/maven

you can validate the maven with help of this command

/usr/share/maven/bin/mvn validate

![image](https://github.com/arjunedify/Arjun/assets/132984407/8162a24d-8a5d-47e1-afbd-71a2e50c5b7f)

To get ip address
 curl ifconfig.io

Now goto Jenkins

Create a pipeline project

![image](https://github.com/arjunedify/Arjun/assets/132984407/62bc18fd-d88c-46a2-be5a-dc233f4c4d10)

![image](https://github.com/arjunedify/Arjun/assets/132984407/da65938d-9014-4a44-b1a3-b698041da27c)

![image](https://github.com/arjunedify/Arjun/assets/132984407/4f6cd62e-6ec0-4546-ae7e-fe6c4cadcbcf)

![image](https://github.com/arjunedify/Arjun/assets/132984407/95b9e86a-0d63-43b3-86e1-2311224a22f1)

Create a Free style project to validate a code :

Add github URL
![image](https://github.com/arjunedify/Arjun/assets/132984407/12e59eb6-f225-437c-a810-781a8f316380)

![image](https://github.com/arjunedify/Arjun/assets/132984407/851e2216-48a3-4e13-a06c-88acb630dbec)

![image](https://github.com/arjunedify/Arjun/assets/132984407/602a25b7-6abb-4bf7-bfd6-96b2b16646d5)

Webhooks configure

Go repository setting \> webhooks\> add webhooks

http://35.169.107.8:8080/github-webhook/

Same for validate , build

/usr/share/maven/bin/mvn validate

/usr/share/maven/bin/mvn package

**Instead of Separate jobs we can club all this job into a single job with help of Jenkins files**

Jenkinsfile

_ **Jenkinsfile** _ is a text file that contains the definition of a Jenkins Pipeline and is checked into source .

Note : it should be same format as written above Don't use Capital letters.

[https://www.jenkins.io/doc/book/pipeline/jenkinsfile/](https://www.jenkins.io/doc/book/pipeline/jenkinsfile/)

pipeline {

agent any

stages {

stage('Build') {

steps {

echo 'Building..'

}

}

stage('Test') {

steps {

echo 'Testing..'

}

}

stage('Deploy') {

steps {

echo 'Deploying....'

}

}

}

}

Creating project using Jenkinsfile

![image](https://github.com/arjunedify/Arjun/assets/132984407/788e37cf-6afe-4e29-9516-fa9db06ebd43)

Method 1 :

![image](https://github.com/arjunedify/Arjun/assets/132984407/5b3a981c-d138-4c55-962e-ab26a9735678)

You can write a pipeline script here direct

Method 2:

Add a Jenkinsfile in github repo

![image](https://github.com/arjunedify/Arjun/assets/132984407/238d236d-a92b-4b90-8a27-582fa6ea1197)

**Configuring Github webhook triggers**

**Goto Jenkins job configuration**

![image](https://github.com/arjunedify/Arjun/assets/132984407/cc2aa08b-3e92-423e-96b2-a92182974bca)

**Now goto Your github repository settings**

**Configure webhooks there . Ipaddress:8080-webhooks/**

![image](https://github.com/arjunedify/Arjun/assets/132984407/9de56549-c722-4523-9cfa-42857bc4bb77)

![image](https://github.com/arjunedify/Arjun/assets/132984407/8064aef2-4017-4541-93db-b60b88c4ae1f)

pipeline {

agent any

stages {

stage('Build') {

steps {

echo 'Building..'

}

}

stage('Test') {

steps {

echo 'Testing..'

}

}

stage('Deploy') {

steps {

echo 'Deploying....'

}

}

}

}

**[centos@ip-172-31-16-244 .git]$ cd /var/lib/jenkins/workspace**

**[centos@ip-172-31-16-244 workspace]$ ls**

**Pipeline\_project Pipeline\_project@tmp pipelintest**

**[centos@ip-172-31-16-244 workspace]$ cd Pipeline\_project**

**[centos@ip-172-31-16-244 Pipeline\_project]$ ls**

**Jenkinsfile pom.xml src target test.txt**

**[centos@ip-172-31-16-244 Pipeline\_project]$ cd target**
