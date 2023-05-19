**LMS-AWS-PIPELINE**

![image](https://github.com/arjunedify/Arjun/assets/130965749/b1e5e5cc-b61e-4e1c-a9d9-8a98552a5ba7)


- For learning continuous integration and continuous delivery(CI/CD) via AWS CodePipeline purposes, we deploy a LMS Application.
- The Application code is present in the below Github link

 [
# digitaledify/lms-public (github.com)
](https://github.com/digitaledify/lms-public)

**Steps that we will follow:**

1. Create IAM Role for EC2 and AWS CodeDeploy
2. Launch an EC2 instance
3. Create a CodePipeline using Github, CodeBuild and CodeDeploy
4. Access your ReactJS app on EC2 public DNS

**1. Create IAM Role for EC2 and AWS CodeDeploy**

AWS service roles are used to grant permissions to an AWS service so it can access AWS resources. The policies that you attach to the service role determine which AWS resources the service can access and what it can do with those resources.

Let's navigate to our AWS Management Console and search for [**IAM**](https://aws.amazon.com/iam/) service. Now create a new role for EC2 and AWS CodeDeploy:

![image](https://github.com/arjunedify/Arjun/assets/130965749/c29bdd5d-ae4f-4b5b-b825-9b1e657530eb)

Identity and Access Management (IAM) — Roles Dashboard

![image](https://github.com/arjunedify/Arjun/assets/130965749/ae8aaf9e-8d0a-4b9c-a2cf-1e63b54ae45b)

Create a new role for EC2 and attach  **AmazonS3ReadOnlyAccess**  policy which will allow our EC2 instance to access stored artifacts from the [Amazon S3](https://aws.amazon.com/s3/) bucket.

![image](https://github.com/arjunedify/Arjun/assets/130965749/af541c43-12d9-4f5e-b8b5-94c7a46620a7)

Create a new service role for CodeDeploy and attach  **AWSCodeDeployRole**  policy which will provide the permissions for our service role to read tags of our EC2 instance, publish information to Amazon SNS topics and much [more](https://docs.aws.amazon.com/codedeploy/latest/userguide/getting-started-create-service-role.html)

![image](https://github.com/arjunedify/Arjun/assets/130965749/2061e5af-07ec-4707-9125-fa7532912c41)

![image](https://github.com/arjunedify/Arjun/assets/130965749/18077f70-cce4-4e4f-b8ba-4e79e5bba821)

**2. Launch an EC2 instance**

Now, let's launch our EC2 instance! Under AWS Management Console, Click on the  **EC2 ** under  **Compute ** which ** ** will take us to the  **EC2 Dashboard**  page. Now click on _ **Launch Instance:** _

![image](https://github.com/arjunedify/Arjun/assets/130965749/503648f6-590d-4393-9980-15208f55459a)
![image](https://github.com/arjunedify/Arjun/assets/130965749/b423d694-8378-4c26-8953-0bbdc12fe30d)

**EC2 Dashboard**

![image](https://github.com/arjunedify/Arjun/assets/130965749/aae26d42-7269-4925-a9a4-641c1380c11d)

We will choose  **Amazon Linux 2 AMI** as our** Amazon Machine Image(AMI)** for launching our instance

![image](https://github.com/arjunedify/Arjun/assets/130965749/5256c13b-31e9-469b-a54a-ec2189eb29ae)

**Choose an Instance Type**

![image](https://github.com/arjunedify/Arjun/assets/130965749/9e35c6e1-31aa-465f-a19b-2bc35b5d5c1e)

You can choose your default VPC (configured for you by AWS) next to  **Network. ** Also, choose the ** IAM role ** we created earlier for EC2 with  **AmazonS3ReadOnlyAccess ** policy ** ** attached

![image](https://github.com/arjunedify/Arjun/assets/130965749/cb3e436f-bf18-491b-b90f-d4d3e70d57c6)

Our instance will be launched with the above storage device settings. You can attach additional EBS volumes and instance store volumes to your instance, or edit the settings of the root volume.

![image](https://github.com/arjunedify/Arjun/assets/130965749/7e9cd983-9283-4d7d-97e9-9fe04e019351)

To help you manage your instances, images, and other Amazon EC2 resources, you can optionally assign your own metadata to each resource in the form of [_ **tags** _](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_Tags.html)

![image](https://github.com/arjunedify/Arjun/assets/130965749/088f79fa-1570-4d72-bb66-f8673cd28844)

![image](https://github.com/arjunedify/Arjun/assets/130965749/4cec2b46-3d60-49de-a1c6-66735011c382)

On this page, you can add firewall rules to allow specific traffic to reach your instance

![image](https://github.com/arjunedify/Arjun/assets/130965749/2fe79aef-aa11-421e-a970-c5a3b7af6e68)

Now you will be prompt to review your instance configuration and create a key pair which allows you to to [connect to your EC2 instance](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-connect-methods.html). Use an existing key or create a new key pair and click ** Download Key Pair ** which will download .pem key to your PC. ** ** After downloading Key Pair, select _ **Launch Instances** _ and wait for your instance to be launched. You will now be able to click on _ **View Instances** _ to go back to your EC2 dashboard where you will see the instance up and running in just a few minutes.

![image](https://github.com/arjunedify/Arjun/assets/130965749/da01209b-e528-4ede-bfd4-d33134f37b14)
![image](https://github.com/arjunedify/Arjun/assets/130965749/e43b1798-dca3-4ac3-9dcc-04c36d274cd8)

Here we go, you've now successfully launched your EC2 instance

Now connect to your EC2 instance by following instructions in [this](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-connect-methods.html) article and [install/reinstall the CodeDeploy agent on your EC2](https://docs.aws.amazon.com/codedeploy/latest/userguide/codedeploy-agent-operations-install-linux.html) instance:

**For Ubuntu**

[https://docs.aws.amazon.com/codedeploy/latest/userguide/codedeploy-agent-operations-install-ubuntu.html](https://docs.aws.amazon.com/codedeploy/latest/userguide/codedeploy-agent-operations-install-ubuntu.html)

\> sudo apt update -y

\> sudo apt install ruby-full -y

\> sudo apt install wget -y

\> cd /home/ubuntu

\> wget [https://](https://bucket-name.s3.region-identifier.amazonaws.com/latest/install)[**bucket-name**](https://bucket-name.s3.region-identifier.amazonaws.com/latest/install)[.s3.](https://bucket-name.s3.region-identifier.amazonaws.com/latest/install)[**region-identifier**](https://bucket-name.s3.region-identifier.amazonaws.com/latest/install)[.amazonaws.com/latest/install](https://bucket-name.s3.region-identifier.amazonaws.com/latest/install)

\> wget [https://](https://aws-codedeploy-us-east-2.s3.us-east-2.amazonaws.com/latest/install)[aws-codedeploy-us-east-2](https://aws-codedeploy-us-east-2.s3.us-east-2.amazonaws.com/latest/install)[.s3.us-east-2.amazonaws.com/latest/install](https://aws-codedeploy-us-east-2.s3.us-east-2.amazonaws.com/latest/install)

\> chmod +x ./install

\> sudo ./install auto

\> sudo service codedeploy-agent status

\> sudo service codedeploy-agent start

\> sudo service codedeploy-agent status

**For AMAZON / CENTOS**

sudo yum update
 sudo yum install ruby
 sudo yum install wget

cd /home/ec2-user
 wget [https://bucket-name.s3.region-identifier.amazonaws.com/latest/install](https://bucket-name.s3.region-identifier.amazonaws.com/latest/install)

_bucket-name_ is the name of the Amazon S3 bucket that contains the CodeDeploy Resource Kit files for your region. _region-identifier_ is the identifier for your region. For example, for the US East (Ohio) Region, replace _bucket-name_ with aws-codedeploy-us-east-2 and replace _region-identifier_ with us-east-2.
 chmod +x ./install
 sudo ./install auto

- Check the status of the

sudo service codedeploy-agent status
![image](https://github.com/arjunedify/Arjun/assets/130965749/5e83ecb5-8b1f-4dc0-a408-feccf14e8e75)

Create a CodePipeline using Github, CodeBuild and CodeDeploy

[AWS CodePipeline](https://aws.amazon.com/codepipeline/) is a continuous integration and continuous delivery (CI/CD) AWS service that allows you to automate the release process for your application or service. Every time you commit a code change to your source(GitHub, AWS CodeCommit, etc), CodePipeline automatically builds, tests, and deploys your code based on the release process models you define while initializing your CodePipeline. This enables you to rapidly and reliably deliver features and updates.

[https://github.com/ravi2krishna/aws-ci-cd-lms.git](https://github.com/ravi2krishna/aws-ci-cd-lms.git)

In the following sections, we will go through the CI/CD pipeline stages:

Step 1: CodePipeline

Step 2: Code Source (CodeCommit or Github)

Step 3: CodeBuild and Build Specification (buildspec.yaml) File

Step 4: CodeDeploy and Application Specification (appspec.yml ) File

Step 5: Review

Step 1: CodePipeline

Let's navigate to CodePipeline via AWS Management Console and click on  **Create pipeline:**

![image](https://github.com/arjunedify/Arjun/assets/130965749/0a7ee78e-0050-468a-b703-421c3f7cfbac)

![image](https://github.com/arjunedify/Arjun/assets/130965749/f2f98df9-5595-4a16-afbd-919c73c99824)

![image](https://github.com/arjunedify/Arjun/assets/130965749/0924da8f-8238-4b06-bc1f-2d545f1cd11b)

![image](https://github.com/arjunedify/Arjun/assets/130965749/844940e1-5a3f-4a40-a247-0a3a934b4007)

![image](https://github.com/arjunedify/Arjun/assets/130965749/bbee995a-8133-4512-b683-6329882789f4)

![image](https://github.com/arjunedify/Arjun/assets/130965749/e3dee7a4-2b6b-4a3c-9295-fa86c61e04ca)

![image](https://github.com/arjunedify/Arjun/assets/130965749/aacfea94-b80c-4fe3-88d8-3ee5652af260)

![image](https://github.com/arjunedify/Arjun/assets/130965749/d621b92f-2920-4bed-afb5-8648427972c0)

![image](https://github.com/arjunedify/Arjun/assets/130965749/d5af06fd-b294-4ca6-812f-f272c73e0ea8)

![image](https://github.com/arjunedify/Arjun/assets/130965749/8565f563-3cb2-4fb1-a3db-1cfc5109de62)

![image](https://github.com/arjunedify/Arjun/assets/130965749/5f8b5206-4c4e-435d-bbe7-beb905110083)

\> vi **buildspec.yaml**

version: 0.2

phases:

pre\_build:

commands:

#installs dependencies into the node\_modules/ directory

- npm install

build:

commands:

- echo Build started on `date`

- echo Compiling

- npm run build

post\_build:

commands:

- echo Build completed on `date`

# Include only the files required for your application to run.

artifacts:

files:

- appspec.yml

- scripts/\*\*/\*

- dist/\*\*/\*

![image](https://github.com/arjunedify/Arjun/assets/130965749/f26d603e-0992-4f8e-9928-2e26035131c3)

![image](https://github.com/arjunedify/Arjun/assets/130965749/c1f5e868-fc4b-4608-9280-5df5fbbf8ab7)

![image](https://github.com/arjunedify/Arjun/assets/130965749/9e23c4fc-dfde-470a-831a-d253d3afae70)

![image](https://github.com/arjunedify/Arjun/assets/130965749/1f0585b3-446f-41d7-9d9f-72ed16bc8847)

![image](https://github.com/arjunedify/Arjun/assets/130965749/2b78901a-0a36-4fd1-b78e-9789bc564cbb)

\> On left menu \> Click Deploy \> Applications (Open in new tab)

![image](https://github.com/arjunedify/Arjun/assets/130965749/5ea509d8-ba92-46f5-8fe0-51436f8fda3a)

![image](https://github.com/arjunedify/Arjun/assets/130965749/0d7e6c32-f272-4877-a345-890566764990)

\> Refresh the options by selecting Deploy Provider : (AWSAppConfig) \>

![image](https://github.com/arjunedify/Arjun/assets/130965749/1a542940-09d6-47ee-970c-a12aee184632)

\> Create Deployment Group

![image](https://github.com/arjunedify/Arjun/assets/130965749/64a6c10a-ada8-4b64-9ee6-4447032e8016)

![image](https://github.com/arjunedify/Arjun/assets/130965749/4dcab900-0a16-4ecf-93d8-cc84e84c19fe)

![image](https://github.com/arjunedify/Arjun/assets/130965749/941f0e46-6a3f-454e-a3f1-ac908a4318dc)

![image](https://github.com/arjunedify/Arjun/assets/130965749/13d40510-8c72-4aeb-bc40-a7b9d57ca9fc)

![image](https://github.com/arjunedify/Arjun/assets/130965749/9b654cd9-6251-4419-8f4d-d954a6e87147)

![image](https://github.com/arjunedify/Arjun/assets/130965749/fa07cfce-4f94-454b-97ed-ea0596b3cfdf)

![image](https://github.com/arjunedify/Arjun/assets/130965749/10c6a340-011f-4956-8596-47a2a06f4d1c)

![image](https://github.com/arjunedify/Arjun/assets/130965749/0c9f5818-ae9a-4779-bcf0-99cc40bcedb6)
![image](https://github.com/arjunedify/Arjun/assets/130965749/d1a0fd59-ef04-4cae-88bd-6495be559eb8)

\> Now go back to Codepipeline Page

\> Refresh the options by selecting Deploy Provider : (AWSAppConfig) \>

![image](https://github.com/arjunedify/Arjun/assets/130965749/54f99c9a-0504-4827-9c85-b687ee359c12)

\> Next \> Create Pipeline

![image](https://github.com/arjunedify/Arjun/assets/130965749/9c92b3b7-be34-417b-9689-f9e55853790c)

![image](https://github.com/arjunedify/Arjun/assets/130965749/2b451dec-e0d1-4817-b284-8107228e3b6d)

![image](https://github.com/arjunedify/Arjun/assets/130965749/0b312d3e-aeda-41c9-a004-172d5dad83e0)
 
