![Shape 2](RackMultipart20230520-1-ydqvai_html_12bdfb4349b113fb.gif)

mubeen

# Terraform Tasks

Task 1

Install & configure Terraform
Create a VPC using Terraform

# **Solution**

Installing terraform

Download terraform from the following link

[https://www.terraform.io/downloads](https://www.terraform.io/downloads)

![](RackMultipart20230520-1-ydqvai_html_62d9f4239eecab33.png)

Path setting for terraform

Got the folder where you download the terraform copy the path and paste in the environment variables

![](RackMultipart20230520-1-ydqvai_html_675e361deb25e039.png)

C:\Users\Abdul Mubeen\Downloads\terraform\_1.1.7\_windows\_386

Right click on my computer

Select properties

![](RackMultipart20230520-1-ydqvai_html_660572825d2abf49.png)

Then goto ![](RackMultipart20230520-1-ydqvai_html_133d13c6d8d4b2a0.png)

![](RackMultipart20230520-1-ydqvai_html_da3e77f3ea7a80c5.png)

After downloading terraform check version by command

$terraform -version

![](RackMultipart20230520-1-ydqvai_html_c793cabebfce9f18.png)

Create IAM user and download access key and secret key for it

Create main.tf

![](RackMultipart20230520-1-ydqvai_html_d427394227ff1c37.png)

Proving aws credentials first that access key and secret key and create a vpc

Then initialized

![](RackMultipart20230520-1-ydqvai_html_346f8e692d0c8880.png)

**\>terraform fmt**

To align the code as per terraform requirement.

![](RackMultipart20230520-1-ydqvai_html_ddc292cb860b0d03.png)

Then

\> **terraform plan**

![](RackMultipart20230520-1-ydqvai_html_899c8e0685100a3d.png)

This terraform plan will display what is going to add and destroy resources

Finally create by using the command

**\> terraform apply**

![](RackMultipart20230520-1-ydqvai_html_1ad9190df1dadcf3.png)

Vpc is created successfully in aws infra.

![](RackMultipart20230520-1-ydqvai_html_d63fbc568e5368b.png)

Task 2

Create VPC & 4 subnets inside the VPC
2- Pub subnet
2- Pvt subnet

Solution :

Creating vpc same as above task 1

Creating subnets 2 public subnets

![](RackMultipart20230520-1-ydqvai_html_1af3a121cbbf6dad.png)

![](RackMultipart20230520-1-ydqvai_html_a1fe6c080a091f65.png)

Creating private subnets

![](RackMultipart20230520-1-ydqvai_html_9c2c34d0f6b02aa4.png)

- **Terraform fmt**
- **Terraform plan**
- **Terraform apply**

![](RackMultipart20230520-1-ydqvai_html_6b1312f4207777dd.png)

![](RackMultipart20230520-1-ydqvai_html_f817c44edf03d8b9.png)

Task 3

Create VPC, 4 subnets configure route table, internet gateway, NACL, 4 Ec2 & Security group
2- Pub subnet install 1 Ec2 in each subnet
2- Pvt subnet install 1 Ec2 in each subnet

**Solution:**

Create VPC using the following terraform script

![](RackMultipart20230520-1-ydqvai_html_31d377cc0c17b910.png)

Creating internet gateway

![](RackMultipart20230520-1-ydqvai_html_6e084588cad758b3.png)

![](RackMultipart20230520-1-ydqvai_html_53e8d530b04543d5.png)

Creating to 2- Pub subnet and installing Ec2 in each subnet

![](RackMultipart20230520-1-ydqvai_html_f8b8d4bbe0350b4.png)

First instance

![](RackMultipart20230520-1-ydqvai_html_58ea40fa72a7f7ae.png)

![](RackMultipart20230520-1-ydqvai_html_736569770f4f7921.png)

 Creating Security group digitalLync\_sg

![](RackMultipart20230520-1-ydqvai_html_e4da63eda377583c.png)

Now creating 2- Pvt subnet install 1 Ec2 in each subnet

![](RackMultipart20230520-1-ydqvai_html_bb0a41585a23d694.png)

Instance in pvt subnet same as above but instead of public subnet select pvt subnet

![](RackMultipart20230520-1-ydqvai_html_955ecb6dac549cb8.png)

Task 4

Create a virialized script the above Task 3

Solution:

Virialized using var.tf calling variable from main.tf instead of directly declaring

![](RackMultipart20230520-1-ydqvai_html_66da82359cc51cb7.png)

![](RackMultipart20230520-1-ydqvai_html_f9951603dbb61e7d.png)

Main.tf file

# provider aws

provider "aws" {

region = var.region

access\_key = var.access\_key

secret\_key = var.secret\_key

}

# Create a VPC

resource "aws\_vpc" "digitalLyncvpc" {

cidr\_block = var.cidr\_block

enable\_dns\_support = true

enable\_dns\_hostnames = true

instance\_tenancy = "default"

tags = {

Name = "digitalLync"

}

}

# creating Public Subnet1

resource "aws\_subnet" "pub\_subnet1" {

vpc\_id = aws\_vpc.digitalLyncvpc.id

cidr\_block = "10.0.1.0/24"

availability\_zone = "us-east-1a"

map\_public\_ip\_on\_launch = "true"

tags = {

Name = "PUB-SB1"

}

}

# creating Public Subnet2

resource "aws\_subnet" "pub\_subnet2" {

vpc\_id = aws\_vpc.digitalLyncvpc.id

cidr\_block = "10.0.2.0/24"

availability\_zone = "us-east-1b"

map\_public\_ip\_on\_launch = "true"

tags = {

Name = "PUB-SB2"

}

}

# creating private Subnet1

resource "aws\_subnet" "pvt\_subnet1" {

vpc\_id = aws\_vpc.digitalLyncvpc.id

cidr\_block = "10.0.3.0/24"

availability\_zone = "us-east-1b"

map\_public\_ip\_on\_launch = "false"

tags = {

Name = "PVB-SB1"

}

}

# creating private Subnet2

resource "aws\_subnet" "pvt\_subnet2" {

vpc\_id = aws\_vpc.digitalLyncvpc.id

cidr\_block = "10.0.4.0/24"

availability\_zone = "us-east-1b"

map\_public\_ip\_on\_launch = "false"

tags = {

Name = "PVB-SB2"

}

}

# creating Internet Gateway

resource "aws\_internet\_gateway" "digitalLync\_igw" {

vpc\_id = aws\_vpc.digitalLyncvpc.id

tags = {

Name = "IGW"

}

}

# creating Public Route Table

resource "aws\_route\_table" "digitalLync\_pub\_rt" {

vpc\_id = aws\_vpc.digitalLyncvpc.id

tags = {

Name = "PUB-RT"

}

}

output "aws\_route\_table\_public\_ids" {

value = aws\_route\_table.digitalLync\_pub\_rt.id

}

resource "aws\_route" "public\_internet\_gateway" {

route\_table\_id = aws\_route\_table.digitalLync\_pub\_rt.id

destination\_cidr\_block = "0.0.0.0/0"

gateway\_id = aws\_internet\_gateway.digitalLync\_igw.id

}

# Private Route Table

# Default is private

resource "aws\_route\_table" "digitalLync\_pvt\_rt" {

vpc\_id = aws\_vpc.digitalLyncvpc.id

tags = {

Name = "PVT-RT"

}

}

# Public Route Table Association

resource "aws\_route\_table\_association" "digitalLync\_pub\_assoc" {

subnet\_id = aws\_subnet.pub\_subnet1.id

route\_table\_id = aws\_route\_table.digitalLync\_pub\_rt.id

}

# Private Route Table Association

resource "aws\_route\_table\_association" "digitalLync\_pvt\_assoc" {

subnet\_id = aws\_subnet.pvt\_subnet1.id

route\_table\_id = aws\_route\_table.digitalLync\_pvt\_rt.id

}

# digitalLync Security Group

resource "aws\_security\_group" "digitalLync\_sg" {

name = "allow\_sshhttp"

description = "Allow sshhttp inbound traffic"

vpc\_id = aws\_vpc.digitalLyncvpc.id

ingress {

description = "ssh from everywhere"

from\_port = 22

to\_port = 22

protocol = "tcp"

cidr\_blocks = ["0.0.0.0/0"]

}

ingress {

description = "http from everywhere"

from\_port = 80

to\_port = 80

protocol = "tcp"

cidr\_blocks = ["0.0.0.0/0"]

}

egress {

from\_port = 0

to\_port = 0

protocol = "-1"

cidr\_blocks = ["0.0.0.0/0"]

}

tags = {

Name = "allow\_sshhttp"

}

}

# creating Instance

resource "aws\_instance" "centos7\_instance" {

ami = "ami-011939b19c6bd1492"

instance\_type = "t2.micro"

subnet\_id = aws\_subnet.pub\_subnet1.id

key\_name = "devops"

count = 2

vpc\_security\_group\_ids = [aws\_security\_group.digitalLync\_sg.id]

# user\_data = file("data.sh")

}

![](RackMultipart20230520-1-ydqvai_html_f1032298b1fbf6a6.png)
