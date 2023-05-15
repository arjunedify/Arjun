# Project Pipeline

**Requirements**

Operating System Centos 7:

From AWS marketplace

Git Repository URL:

[https://github.com/mubeen507/project.git](https://github.com/mubeen507/project.git)

Jenkins Download URL:

[https://www.jenkins.io/doc/book/installing/linux/#red-hat-centos](https://www.jenkins.io/doc/book/installing/linux/#red-hat-centos)

**Jenkins installation Steps**

![](RackMultipart20230515-1-7wi1ah_html_d22a7fefe74e77d5.png)

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

![](RackMultipart20230515-1-7wi1ah_html_1e55b85dbc57f0d5.png)

Install suggested Plugins

**Install git:**

sudo yum install git -y

**Installing Maven**

[https://maven.apache.org/download.cgi](https://maven.apache.org/download.cgi)

![](RackMultipart20230515-1-7wi1ah_html_bb709e8a5114e2ee.png)

**Copy the url**

wget https://dlcdn.apache.org/maven/maven-3/3.9.1/binaries/apache-maven-3.9.1-bin.tar.gz

ls

tar -xf apache-maven-3.9.1-bin.tar.gz

cp -rf apache-maven-3.9.1 maven

now move the maven to usr share directory

mv maven /usr/share/maven

you can validate the maven with help of this command

/usr/share/maven/bin/mvn validate

![](RackMultipart20230515-1-7wi1ah_html_e4d6a46e9817afe7.png)

To get ip address
 curl ifconfig.io

Now goto Jenkins

Create a pipeline project

![](RackMultipart20230515-1-7wi1ah_html_923ed59c70361b49.png)

![](RackMultipart20230515-1-7wi1ah_html_1ce491a43ba1ceae.png)

![](RackMultipart20230515-1-7wi1ah_html_65332ff34dd13fb3.png)

![](RackMultipart20230515-1-7wi1ah_html_56b62aca842f6584.png)

Create a Free style project to validate a code :

Add github URL

![](RackMultipart20230515-1-7wi1ah_html_a9475d88a8f489d0.png)

![](RackMultipart20230515-1-7wi1ah_html_40b812e8080c5180.png)

![](RackMultipart20230515-1-7wi1ah_html_a957e079b229ba9a.png)

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

![](RackMultipart20230515-1-7wi1ah_html_19256e056f5bbb6e.png)

Method 1 :

![](RackMultipart20230515-1-7wi1ah_html_2917f7bd0e2334c3.png)

You can write a pipeline script here direct

Method 2:

Add a Jenkinsfile in github repo

![](RackMultipart20230515-1-7wi1ah_html_ea3ff8ecc233fbfb.png)

**Configuring Github webhook triggers**

**Goto Jenkins job configuration**

![](RackMultipart20230515-1-7wi1ah_html_e650abb27313faf4.png)

**Now goto Your github repository settings**

**Configure webhooks there . Ipaddress:8080-webhooks/**

![](RackMultipart20230515-1-7wi1ah_html_f8ec8a91d3c13a27.png)

![](RackMultipart20230515-1-7wi1ah_html_33670701262b3bea.png)

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
