**LMS-AWS-PIPELINE**

![](RackMultipart20230519-1-5krc33_html_c4c9ea1d80fe0e82.jpg)

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

![](RackMultipart20230519-1-5krc33_html_e4f2e839922b2aad.png)

Identity and Access Management (IAM) — Roles Dashboard

![](RackMultipart20230519-1-5krc33_html_269d6f7ebb36488b.png)

Create a new role for EC2 and attach  **AmazonS3ReadOnlyAccess**  policy which will allow our EC2 instance to access stored artifacts from the [Amazon S3](https://aws.amazon.com/s3/) bucket.

![](RackMultipart20230519-1-5krc33_html_b491d847ee60d608.png)

Create a new service role for CodeDeploy and attach  **AWSCodeDeployRole**  policy which will provide the permissions for our service role to read tags of our EC2 instance, publish information to Amazon SNS topics and much [more](https://docs.aws.amazon.com/codedeploy/latest/userguide/getting-started-create-service-role.html)

![](RackMultipart20230519-1-5krc33_html_4017239daa15034f.png)

![](RackMultipart20230519-1-5krc33_html_f3695df62caadd72.png)

**2. Launch an EC2 instance**

Now, let's launch our EC2 instance! Under AWS Management Console, Click on the  **EC2 ** under  **Compute ** which ** ** will take us to the  **EC2 Dashboard**  page. Now click on _ **Launch Instance:** _

![](RackMultipart20230519-1-5krc33_html_836736083eb6a8ef.png)

![](RackMultipart20230519-1-5krc33_html_f233b1448e952df4.png)

**EC2 Dashboard**

![](RackMultipart20230519-1-5krc33_html_de1a093a30d58c46.png)

We will choose  **Amazon Linux 2 AMI** as our** Amazon Machine Image(AMI)** for launching our instance

![](RackMultipart20230519-1-5krc33_html_6ef424ef8f865924.png)

**Choose an Instance Type**

![](RackMultipart20230519-1-5krc33_html_ed25d44184f228b5.png)

You can choose your default VPC (configured for you by AWS) next to  **Network. ** Also, choose the ** IAM role ** we created earlier for EC2 with  **AmazonS3ReadOnlyAccess ** policy ** ** attached

![](RackMultipart20230519-1-5krc33_html_72031fc0b4b3f142.png)

Our instance will be launched with the above storage device settings. You can attach additional EBS volumes and instance store volumes to your instance, or edit the settings of the root volume.

![](RackMultipart20230519-1-5krc33_html_75b663b393438a05.png)

To help you manage your instances, images, and other Amazon EC2 resources, you can optionally assign your own metadata to each resource in the form of [_ **tags** _](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_Tags.html)

![](RackMultipart20230519-1-5krc33_html_3456a64ebbf741f1.png)

![](RackMultipart20230519-1-5krc33_html_ff638fc5f05dde94.png)

On this page, you can add firewall rules to allow specific traffic to reach your instance

![](RackMultipart20230519-1-5krc33_html_42776de67acfbb3e.png)

Now you will be prompt to review your instance configuration and create a key pair which allows you to to [connect to your EC2 instance](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-connect-methods.html). Use an existing key or create a new key pair and click ** Download Key Pair ** which will download .pem key to your PC. ** ** After downloading Key Pair, select _ **Launch Instances** _ and wait for your instance to be launched. You will now be able to click on _ **View Instances** _ to go back to your EC2 dashboard where you will see the instance up and running in just a few minutes.

![](RackMultipart20230519-1-5krc33_html_571334682c2761d0.png)

![](RackMultipart20230519-1-5krc33_html_6059df8d49bcdd2.png)

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

![](RackMultipart20230519-1-5krc33_html_a33b342736937ac2.png)

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

![](RackMultipart20230519-1-5krc33_html_47766456a5959b01.png)

![](RackMultipart20230519-1-5krc33_html_e4a73cc9a9178702.png)

![](RackMultipart20230519-1-5krc33_html_6104af55131adc82.png)

![](RackMultipart20230519-1-5krc33_html_ceedddb8be360c70.png)

![](RackMultipart20230519-1-5krc33_html_dc55ff0157ff26f2.png)

![](RackMultipart20230519-1-5krc33_html_59d08be7fb8ee409.png)

![](RackMultipart20230519-1-5krc33_html_59d08be7fb8ee409.png)

![](RackMultipart20230519-1-5krc33_html_c7d285f864f585.png)

![](RackMultipart20230519-1-5krc33_html_34dcebedd2b9d3b0.png)

![](RackMultipart20230519-1-5krc33_html_6001eeb4f9932467.png)

![](RackMultipart20230519-1-5krc33_html_c85f5a026913d139.png)

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

![](RackMultipart20230519-1-5krc33_html_86d7e3715ea1aab8.png)

![](RackMultipart20230519-1-5krc33_html_354c6f0d737f655a.png)

![](RackMultipart20230519-1-5krc33_html_eca89fb07ea2e8ad.png)

![](RackMultipart20230519-1-5krc33_html_6e21e79e1a11ee32.png)

![](RackMultipart20230519-1-5krc33_html_83be4144c840136.png)

\> On left menu \> Click Deploy \> Applications (Open in new tab)

![](RackMultipart20230519-1-5krc33_html_3a2f4216ba008cea.png)

![](RackMultipart20230519-1-5krc33_html_6f21ae4c1920656e.png)

\> Refresh the options by selecting Deploy Provider : (AWSAppConfig) \>

![](RackMultipart20230519-1-5krc33_html_59136644b4907dde.png)

\> Create Deployment Group

![](RackMultipart20230519-1-5krc33_html_86ffa12f3f1bf809.png)

![](RackMultipart20230519-1-5krc33_html_9a51ba05347d3c30.png)

![](RackMultipart20230519-1-5krc33_html_f3759365a2efee7f.png)

![](RackMultipart20230519-1-5krc33_html_dbde4dfb821d145c.png)

![](RackMultipart20230519-1-5krc33_html_c27ba0f568c6a9d1.png)

![](RackMultipart20230519-1-5krc33_html_9e2918470d2946ec.png)

![](RackMultipart20230519-1-5krc33_html_a33b342736937ac2.png)

![](RackMultipart20230519-1-5krc33_html_6f36580cd6de58b4.png)

![](RackMultipart20230519-1-5krc33_html_b96c51a59209d5cc.png)

\> Now go back to Codepipeline Page

\> Refresh the options by selecting Deploy Provider : (AWSAppConfig) \>

![](RackMultipart20230519-1-5krc33_html_a4ca73e1d837d03e.png)

\> Next \> Create Pipeline

![](RackMultipart20230519-1-5krc33_html_b258d327eecba4c8.png)

![](RackMultipart20230519-1-5krc33_html_1b34f4da8a39fc01.png)

![](RackMultipart20230519-1-5krc33_html_e1d22dd61fc0e4fa.png)

![](RackMultipart20230519-1-5krc33_html_5e546c7e05f9aed.png)
