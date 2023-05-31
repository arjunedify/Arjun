
# Terraform Tasks

Task 1

Install & configure Terraform
Create a VPC using Terraform

# **Solution**

Installing terraform

Download terraform from the following link

[https://www.terraform.io/downloads](https://www.terraform.io/downloads)
![image](https://github.com/arjunedify/Arjun/assets/130965749/231167cd-ccfa-4e03-8f8e-21419c396ce2)
Path setting for terraform

Got the folder where you download the terraform copy the path and paste in the environment variables

![image](https://github.com/arjunedify/Arjun/assets/130965749/ed9d442e-983c-4b32-b340-a2402f33eab1)

C:\Users\Abdul Mubeen\Downloads\terraform\_1.1.7\_windows\_386

Right click on my computer

Select properties

![image](https://github.com/arjunedify/Arjun/assets/130965749/c8c1433d-4623-4346-95ca-eb25ce8e0015)

Then goto ![](RackMultipart20230520-1-ydqvai_html_133d13c6d8d4b2a0.png)

![image](https://github.com/arjunedify/Arjun/assets/130965749/c8e4dd76-da01-4702-a55b-3f60a907c8e0)

After downloading terraform check version by command
```
terraform -version
```
![image](https://github.com/arjunedify/Arjun/assets/130965749/f7ea7a23-5f4a-4c1e-8a19-2fb1ccee6e5b)

Create IAM user and download access key and secret key for it

Create main.tf

![image](https://github.com/arjunedify/Arjun/assets/130965749/83b310ca-55ad-45f7-855d-30d52db8dad9)

Proving aws credentials first that access key and secret key and create a vpc

Then initialized

![image](https://github.com/arjunedify/Arjun/assets/130965749/7afb5681-d209-4368-aa25-0f8ebd4af8dc)

**\>terraform fmt**

To align the code as per terraform requirement.

![image](https://github.com/arjunedify/Arjun/assets/130965749/1b0f9561-b4c4-4cc1-ba5d-cccfef7c5460)

Then

\> **terraform plan**

![image](https://github.com/arjunedify/Arjun/assets/130965749/ccc1d99a-c752-419d-aa5c-a85a33ac0063)

This terraform plan will display what is going to add and destroy resources

Finally create by using the command

**\> terraform apply**

![image](https://github.com/arjunedify/Arjun/assets/130965749/440a03d0-8edf-4f49-acfe-8fab19fa7f5b)

Vpc is created successfully in aws infra.

![image](https://github.com/arjunedify/Arjun/assets/130965749/f2ce6217-a74a-4dca-a9dc-0fc3dcacefef)

Task 2

Create VPC & 4 subnets inside the VPC
2- Pub subnet
2- Pvt subnet

Solution :

Creating vpc same as above task 1

Creating subnets 2 public subnets

![image](https://github.com/arjunedify/Arjun/assets/130965749/d01f65dd-d40e-486b-9b3e-e4a9b7c27a9e)
![image](https://github.com/arjunedify/Arjun/assets/130965749/0b330123-6936-4a2c-bf86-9b1d5effd409)

Creating private subnets

![image](https://github.com/arjunedify/Arjun/assets/130965749/a2db98c9-164c-4d51-bf56-3a3a065f261b)

- **Terraform fmt**
- **Terraform plan**
- **Terraform apply**

![image](https://github.com/arjunedify/Arjun/assets/130965749/1c31fe18-0773-4329-aaff-907404d505d8)

![image](https://github.com/arjunedify/Arjun/assets/130965749/55f78cf2-6372-4dab-aa1a-8436f409cd75)

Task 3

Create VPC, 4 subnets configure route table, internet gateway, NACL, 4 Ec2 & Security group
2- Pub subnet install 1 Ec2 in each subnet
2- Pvt subnet install 1 Ec2 in each subnet

**Solution:**

Create VPC using the following terraform script

![image](https://github.com/arjunedify/Arjun/assets/130965749/ae20438a-80a1-4121-bd4f-4da54cd27ae2)

Creating internet gateway

![image](https://github.com/arjunedify/Arjun/assets/130965749/29061a38-cb25-4308-bb32-7e2118af635c)

![image](https://github.com/arjunedify/Arjun/assets/130965749/1d7cdfc8-d710-4ecb-8517-60a5dc8002fc)

Creating to 2- Pub subnet and installing Ec2 in each subnet
![image](https://github.com/arjunedify/Arjun/assets/130965749/ebd1acdf-6723-4946-906d-8e864ba0002b)

First instance

![image](https://github.com/arjunedify/Arjun/assets/130965749/7015c7c0-1270-47c3-a7d3-61a4b8bc95cc)

![image](https://github.com/arjunedify/Arjun/assets/130965749/cd68616a-61be-4ffa-880c-3277d83cd445)

 Creating Security group digitalLync\_sg

![image](https://github.com/arjunedify/Arjun/assets/130965749/0d576523-d685-45e2-9463-fd8d8e120b21)

Now creating 2- Pvt subnet install 1 Ec2 in each subnet
![image](https://github.com/arjunedify/Arjun/assets/130965749/4eb892b2-49f4-4802-8cf9-b99bcb6587d6)

Instance in pvt subnet same as above but instead of public subnet select pvt subnet

![image](https://github.com/arjunedify/Arjun/assets/130965749/ddc287bd-674a-446c-a6ae-3729e1524a45)

Task 4

Create a virialized script the above Task 3

Solution:

Virialized using var.tf calling variable from main.tf instead of directly declaring

![image](https://github.com/arjunedify/Arjun/assets/130965749/f925d9bb-c6e6-4cd9-b39d-14f97a4ba404)

![image](https://github.com/arjunedify/Arjun/assets/130965749/b217b8d8-627c-4edf-8fcc-b77ba62d33d3)

Main.tf file

# provider aws
 ```
provider "aws" {

region = var.region

access\_key = var.access\_key

secret\_key = var.secret\_key

}
```
# Create a VPC
```
resource "aws\_vpc" "digitalLyncvpc" {

cidr\_block = var.cidr\_block

enable\_dns\_support = true

enable\_dns\_hostnames = true

instance\_tenancy = "default"

tags = {

Name = "digitalLync"

}

}
```
# creating Public Subnet1
```
resource "aws\_subnet" "pub\_subnet1" {

vpc\_id = aws\_vpc.digitalLyncvpc.id

cidr\_block = "10.0.1.0/24"

availability\_zone = "us-east-1a"

map\_public\_ip\_on\_launch = "true"

tags = {

Name = "PUB-SB1"

}

}
```
# creating Public Subnet2
```
resource "aws\_subnet" "pub\_subnet2" {

vpc\_id = aws\_vpc.digitalLyncvpc.id

cidr\_block = "10.0.2.0/24"

availability\_zone = "us-east-1b"

map\_public\_ip\_on\_launch = "true"

tags = {

Name = "PUB-SB2"

}

}
```
# creating private Subnet1
```
resource "aws\_subnet" "pvt\_subnet1" {

vpc\_id = aws\_vpc.digitalLyncvpc.id

cidr\_block = "10.0.3.0/24"

availability\_zone = "us-east-1b"

map\_public\_ip\_on\_launch = "false"

tags = {

Name = "PVB-SB1"

}

}
```
# creating private Subnet2
```
resource "aws\_subnet" "pvt\_subnet2" {

vpc\_id = aws\_vpc.digitalLyncvpc.id

cidr\_block = "10.0.4.0/24"

availability\_zone = "us-east-1b"

map\_public\_ip\_on\_launch = "false"

tags = {

Name = "PVB-SB2"

}

}
```
# creating Internet Gateway
```
resource "aws\_internet\_gateway" "digitalLync\_igw" {

vpc\_id = aws\_vpc.digitalLyncvpc.id

tags = {

Name = "IGW"

}

}
```
# creating Public Route Table
```
resource "aws\_route\_table" "digitalLync\_pub\_rt" {

vpc\_id = aws\_vpc.digitalLyncvpc.id

tags = {

Name = "PUB-RT"

}

}

output "aws\_route\_table\_public\_ids" {

value = aws\_route\_table.digitalLync\_pub\_rt.id

}
```
**Public route Table attch to internet gateway**
```
resource "aws\_route" "public\_internet\_gateway" {

route\_table\_id = aws\_route\_table.digitalLync\_pub\_rt.id

destination\_cidr\_block = "0.0.0.0/0"

gateway\_id = aws\_internet\_gateway.digitalLync\_igw.id

}
```
# Private Route Table

# Default is private
```
resource "aws\_route\_table" "digitalLync\_pvt\_rt" {

vpc\_id = aws\_vpc.digitalLyncvpc.id

tags = {

Name = "PVT-RT"

}

}
```
# Public Route Table Association
```
resource "aws\_route\_table\_association" "digitalLync\_pub\_assoc" {

subnet\_id = aws\_subnet.pub\_subnet1.id

route\_table\_id = aws\_route\_table.digitalLync\_pub\_rt.id

}
```
# Private Route Table Association
```
resource "aws\_route\_table\_association" "digitalLync\_pvt\_assoc" {

subnet\_id = aws\_subnet.pvt\_subnet1.id

route\_table\_id = aws\_route\_table.digitalLync\_pvt\_rt.id

}
```
# digitalLync Security Group
```
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
```
# creating Instance
```
resource "aws\_instance" "centos7\_instance" {

ami = "ami-011939b19c6bd1492"

instance\_type = "t2.micro"

subnet\_id = aws\_subnet.pub\_subnet1.id

key\_name = "devops"

count = 2

vpc\_security\_group\_ids = [aws\_security\_group.digitalLync\_sg.id]

# user\_data = file("data.sh")

}
```
![image](https://github.com/arjunedify/Arjun/assets/130965749/e1fad663-ac87-437f-bf86-dd96424109b7)
