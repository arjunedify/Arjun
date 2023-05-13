# **Create AWS Account**

- Visit - aws.amazon.com
![image](https://user-images.githubusercontent.com/130965749/237010109-1aaff2be-cb24-4294-a915-d16640fd2735.png)

![image](https://user-images.githubusercontent.com/130965749/237010259-b1bc3cfb-551e-4ff3-8f0f-a2fc551c6bd3.png)

**Setting up AWS Account**

- The AWS Free Tier enables you to gain free, hands-on experience with the AWS platform, products, and services.

- These free tier offers are only available to new AWS customers, and are available for 12 months following your AWS sign-up date.

- [FREE TIER FEATURES](https://aws.amazon.com/free/) and you can register an account in same page

- [Visit](https://aws.amazon.com/free/)

- Click the button to " **Create an AWS Account**"

- On the next page, provide your Email Address, Password, and AWS Account Name (you can change this name in your account settings after sign up).

- Click " **Continue**" to proceed

![image](https://user-images.githubusercontent.com/130965749/237010454-3572ddbc-9530-49b1-828f-e3bee3df4f72.png)

- Next, you'll provide your contact information. If you're registering as an individual, select " **Personal**" and if you're using any business, select "Company"

- Complete the remaining fields with your information. Then click "Create Account and Continue" to proceed.

![image](https://user-images.githubusercontent.com/130965749/237010506-23be796d-a27f-41d1-aa53-b2a72cf67bb3.png)

- Next, you'll be asked to provide a credit card for your AWS Account.

- Once you've completed this information, click the "Secure Submit" button to proceed.

- Next, you'll be asked to complete a brief phone verification step. Here, you are asked to provide a phone number where you can be reached, and to click the "Call Me Now" button to receive an automated phone call.

- Once you receive the call, you'll input the number shown on your screen using your dial-pad

![image](https://user-images.githubusercontent.com/130965749/237010721-c05720cc-6082-437d-9832-8999ff974e59.png)

![image](https://user-images.githubusercontent.com/130965749/237010821-baf65186-90d5-4d91-be89-b8c30b6f6b72.png)

![image](https://user-images.githubusercontent.com/130965749/237010941-1293f8aa-b408-4bfb-832f-e802f296fba6.png)

![image](https://user-images.githubusercontent.com/130965749/237011010-5988431a-c530-49b3-80f9-4b624e18f5ee.png)

# **Create AZURE Account**

- The **Azure account** is a global unique entity that **gets you access** to **Azure Services** and your **Azure subscriptions**.

- To start using the services we need an Azure Account

- To create an Azure Account, we need a **Phone Number** , **Email ID** & **Credit/Debit Card**.

\> **For 1st month Azure provides a Free Trial Subscription credits worth of $ 200 i.e Rs14,500**

\> After one month if you want to continue to use it, we need to upgrade from the Free Trial to Pay as You Go model i.e Only Pay for what we use.

\> You can use an Outlook account or any gmail account is also fine.

\> But as we started moving towards microsoft products, let's create an outlook account

\> Search for **create an azure account** \>

![image](https://user-images.githubusercontent.com/130965749/237011092-be9c8cc1-33fe-4342-85ba-23bc2bc10ebf.png)

- Click on [this URL](https://azure.microsoft.com/en-us/free/), and here click on the **Start free** button.

![image](https://user-images.githubusercontent.com/130965749/237011182-ab8f8d70-c92c-4ba5-997f-67072bda8c3b.png)

![image](https://github.com/arjunedify/Arjun/assets/132984407/733daee2-4988-4410-a775-c7b54eb2a9cf)

![image](https://github.com/arjunedify/Arjun/assets/132984407/1d220088-0c9b-4696-a740-8afda36b9a34)

![image](https://github.com/arjunedify/Arjun/assets/132984407/3ab7b543-d277-49db-9c96-1484d28021bf)

![image](https://github.com/arjunedify/Arjun/assets/132984407/283de6a1-30b6-49ea-93f8-1047784f7e4b)

![image](https://github.com/arjunedify/Arjun/assets/132984407/106a9520-26e3-4d77-9e83-e0b64feb1c93)

# **Create AZURE VM**

# **Create AWS EC2 Instance**

# **Install Putty**

**Setup Putty**

- Visit following site and **Install Putty**
  - [https://www.putty.org/](https://www.putty.org/)

# **Convert pem file to ppk file**

**Convert your private key using PuTTYgen**

- PuTTY does not natively support the private key format for SSH keys. PuTTY provides a tool named **PuTTYgen** , which converts keys to the required format for PuTTY. You must convert your private key (.pem file) into this format (.ppk file) as follows in order to connect to your instance using PuTTY.

**To convert your private key**

\> From the **Start** menu, choose **All Programs** , **PuTTY** , **PuTTYgen**.

![image](https://github.com/arjunedify/Arjun/assets/132984407/e0be01b9-4d0b-43dc-8007-79480c03e69a)

\> Choose **Load**. By default, PuTTYgen displays only files with the extension .ppk. To locate your .pem file, choose the option to display files of all types.
 ![image](https://github.com/arjunedify/Arjun/assets/132984407/05fb6d51-5fff-4d92-9a72-bf74c695ddfc)

\> Select your .pem file for the key pair that you specified when you launched your instance and choose **Open**. PuTTYgen displays a notice that the .pem file was successfully imported. Choose **OK**.

![image](https://github.com/arjunedify/Arjun/assets/132984407/47a7ca1d-2907-4bbd-ba56-fa2852fc928d)

\> To save the key in the format that PuTTY can use, choose **Save private key**. PuTTYgen displays a warning about saving the key without a passphrase. Choose **Yes**.

![image](https://github.com/arjunedify/Arjun/assets/132984407/1f3c6f11-f744-4b36-9b52-4bab67d2f6de)

\> Specify the same name for the key that you used for the key pair (for example, my-key-pair) and choose **Save**. PuTTY automatically adds the .ppk file extension.

\> Your private key is now in the correct format for use with PuTTY. You can now connect to your instance using PuTTY's SSH client.

**To connect to your instance using PuTTY**

1. Start PuTTY (from the **Start** menu, choose **All Programs, PuTTY, PuTTY** ).
2. In the **Category** pane, choose **Session** and complete the following fields:
  1. In the **Host Name** box, do one of the following:
    1. enter your public IP Address or Public DNS Name
    2. Ensure that the **Port** value is 22.
    3. Under **Connection type** , select **SSH**.

![image](https://github.com/arjunedify/Arjun/assets/132984407/400c62bf-bda0-4e82-a919-07d42bc8d2c3)

In the **Category** pane, expand **Connection** , expand **SSH** , and then choose **Auth**. Complete the following:

1. Choose **Browse**.
2. Select the .ppk file that you generated for your key pair and choose **Open**.

![image](https://github.com/arjunedify/Arjun/assets/132984407/77299078-8bf6-4e75-be2a-3f9b1f114424)

![image](https://github.com/arjunedify/Arjun/assets/132984407/95dc1dee-8884-448a-ab48-073af1fae570)


\> If this is the first time you have connected to this instance, PuTTY displays a security alert dialog box that asks whether you trust the host to which you are connecting.

![image](https://github.com/arjunedify/Arjun/assets/132984407/ec843014-f1f2-448e-a282-13fdd090b392)

Choose **Yes**. A window opens and you are connected to your instance.

# **Install GitBash**

Once [Git Bash Windows installer](https://git-scm.com/download/win) is downloaded, run the executable file and follow the steps.

![image](https://github.com/arjunedify/Arjun/assets/132984407/c6fb3a8c-5962-4ff1-b4ce-8ec09fcbcf14)

![image](https://github.com/arjunedify/Arjun/assets/132984407/399045c2-6713-4c2c-a0f0-c6a27a4c8d4f)

![image](https://github.com/arjunedify/Arjun/assets/132984407/866d26e3-772e-4e52-8f06-318736d14004)

![image](https://github.com/arjunedify/Arjun/assets/132984407/be979396-6ea6-4080-94bc-03152432e1af)

![image](https://github.com/arjunedify/Arjun/assets/132984407/e0410746-9ffb-4031-b1c0-9f3ddb834c6d)

![image](https://github.com/arjunedify/Arjun/assets/132984407/f5a10d6d-cf90-4dd7-b2ff-0e4ccb189927)

![image](https://github.com/arjunedify/Arjun/assets/132984407/d78475d6-5804-4592-b5ed-06e05e6ab186)

![image](https://github.com/arjunedify/Arjun/assets/132984407/a9ac3510-73c1-445c-9a1e-b80c668badd1)

![image](https://github.com/arjunedify/Arjun/assets/132984407/d45adcb2-ace4-4261-a020-b09c6fce8d29)

![image](https://github.com/arjunedify/Arjun/assets/132984407/7d1f8f33-39bd-48ed-981c-38b7c7fd009d)

![image](https://github.com/arjunedify/Arjun/assets/132984407/6586c38b-3e44-4bab-8150-b5a87170d459)

![image](https://github.com/arjunedify/Arjun/assets/132984407/a093f1d2-7365-4d92-8b51-d09e45a36f1d)

# **Install VS Code**

## How to install Visual Studio code

### Step 1 :

- Download VS code from here [Link](https://code.visualstudio.com/download).

### Step 2 :

- Download the Visual Studio Code installer for Windows. Once it is downloaded, run the installer (VSCodeUserSetup-{version}.exe). Then, run the file – it will only take a minute.  ![](RackMultipart20230508-1-3vex9c_html_714f977015fe534f.png)
- Accept the agreement and click "next."

![](RackMultipart20230508-1-3vex9c_html_76c048ab2db25ab8.png)

- After accepting all the requests press finish button. By default, VS Code installs under:  **"C:\users{username}\AppData\Local\Programs\Microsoft VS Code."**

![](RackMultipart20230508-1-3vex9c_html_3516a5b0fc26d9e9.png)

- If the installation is successful, you will see the following:

![](RackMultipart20230508-1-3vex9c_html_a22d1c0bfd19d942.png)

# **Convert a pem key to ppk key**

##
# PEM to PPK conversion steps

Here are the steps to quickly convert a PEM to a PPK file with PuTTYGen:

1. Download PuTTYGen from [puttygen.com](https://www.puttygen.com/)
2. Open PuTTYGen and click the _Load_ button
3. Set the filetype to  **\*.\***  so the AWS PEM file is visible
4. Select your PEM file and PuTTYGen will import it
5. Click _Save Private Key_ and PuTTYGen will convert the PEM to a PPK file

Step 3 often causes problems, because the file selector is set to PPK so the PEM will not be visible even if you select the correct folder. Just change the filetype to \*.\* and every filetype will be visible.

[![](RackMultipart20230508-1-3vex9c_html_296a4ee361ce6760.jpg)](https://itknowledgeexchange.techtarget.com/coffee-talk/files/2022/02/puttygen-pem-ppk-conversion.jpg)

Upon import, PuTTYgen explains how to convert an SSH PEM to a PPK format for use with PuTTY.

# **Create AZURE VM**

##
 Sign in to Azure

Sign in to the [Azure portal](https://portal.azure.com/).

## Create virtual machine

1. Enter _virtual machines_ in the search.
2. Under  **Services** , select  **Virtual machines**.
3. In the  **Virtual machines**  page, select  **Create**  and then  **Virtual machine**. The  **Create a virtual machine**  page opens.
4. In the  **Basics**  tab, under  **Project details** , make sure the correct subscription is selected and then choose to  **Create new**  resource group. Enter _myResourceGroup_ for the name.\*.

![](RackMultipart20230508-1-3vex9c_html_8698d6e30df3e1c2.png)

1. Under  **Instance details** , enter _myVM_ for the  **Virtual machine name** , and choose _Ubuntu 18.04 LTS - Gen2_ for your  **Image**. Leave the other defaults. The default size and pricing is only shown as an example. Size availability and pricing are dependent on your region and subscription.

![](RackMultipart20230508-1-3vex9c_html_364ec17d322bdcc.png)

  **Note**

Some users will now see the option to create VMs in multiple zones. To learn more about this new capability, see [**Create virtual machines in an availability zone**](https://learn.microsoft.com/en-us/azure/virtual-machines/create-portal-availability-zone).  ![](RackMultipart20230508-1-3vex9c_html_f782e3d2010c8077.png)

1. Under  **Administrator account** , select  **SSH public key**.
2. In  **Username**  enter _azureuser_.
3. For  **SSH public key source** , leave the default of  **Generate new key pair** , and then enter _myKey_ for the  **Key pair name**.

![](RackMultipart20230508-1-3vex9c_html_88f3e94ab69c3cd6.png)

1. Under  **Inbound port rules**  \>  **Public inbound ports** , choose  **Allow selected ports**  and then select **SSH (22)** and **HTTP (80)** from the drop-down.

![](RackMultipart20230508-1-3vex9c_html_6c5aae4413e5e2bc.png)

1. Leave the remaining defaults and then select the  **Review + create**  button at the bottom of the page.
2. On the  **Create a virtual machine**  page, you can see the details about the VM you are about to create. When you are ready, select  **Create**.
3. When the  **Generate new key pair**  window opens, select  **Download private key and create resource**. Your key file will be download as  **myKey.pem**. Make sure you know where the .pem file was downloaded; you will need the path to it in the next step.
4. When the deployment is finished, select  **Go to resource**.
5. On the page for your new VM, select the public IP address and copy it to your clipboard.

![](RackMultipart20230508-1-3vex9c_html_990c94a1cc680ab4.png)

## Connect to virtual machine
