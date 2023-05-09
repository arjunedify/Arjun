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

![](RackMultipart20230508-1-3vex9c_html_64be53ba9ce2e3f5.png)

![](RackMultipart20230508-1-3vex9c_html_5340158465378abf.png)

![](RackMultipart20230508-1-3vex9c_html_f5c3a8374480bd58.png)

![](RackMultipart20230508-1-3vex9c_html_c2ebebb9380607a1.png)

![](RackMultipart20230508-1-3vex9c_html_fdff4379b72cc32d.png)

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

![](RackMultipart20230508-1-3vex9c_html_a2b74e2ae3e92091.png)

\> Choose **Load**. By default, PuTTYgen displays only files with the extension .ppk. To locate your .pem file, choose the option to display files of all types.
 ![](RackMultipart20230508-1-3vex9c_html_3a4d9f199842b762.png)

\> Select your .pem file for the key pair that you specified when you launched your instance and choose **Open**. PuTTYgen displays a notice that the .pem file was successfully imported. Choose **OK**.

![](RackMultipart20230508-1-3vex9c_html_987d080274a60b14.png)

\> To save the key in the format that PuTTY can use, choose **Save private key**. PuTTYgen displays a warning about saving the key without a passphrase. Choose **Yes**.

![](RackMultipart20230508-1-3vex9c_html_b8b5728f0dd55fb4.png)

\> Specify the same name for the key that you used for the key pair (for example, my-key-pair) and choose **Save**. PuTTY automatically adds the .ppk file extension.

\> Your private key is now in the correct format for use with PuTTY. You can now connect to your instance using PuTTY's SSH client.

**To connect to your instance using PuTTY**

1. Start PuTTY (from the **Start** menu, choose **All Programs, PuTTY, PuTTY** ).
2. In the **Category** pane, choose **Session** and complete the following fields:
  1. In the **Host Name** box, do one of the following:
    1. enter your public IP Address or Public DNS Name
    2. Ensure that the **Port** value is 22.
    3. Under **Connection type** , select **SSH**.

![](RackMultipart20230508-1-3vex9c_html_15420e5e2f6790de.png)

In the **Category** pane, expand **Connection** , expand **SSH** , and then choose **Auth**. Complete the following:

1. Choose **Browse**.
2. Select the .ppk file that you generated for your key pair and choose **Open**.

![](RackMultipart20230508-1-3vex9c_html_f9c5945b6cb8ada5.png)

![](RackMultipart20230508-1-3vex9c_html_2f8e057ae1df7959.png)

\> If this is the first time you have connected to this instance, PuTTY displays a security alert dialog box that asks whether you trust the host to which you are connecting.

![](RackMultipart20230508-1-3vex9c_html_11ec9f2860201484.png)

Choose **Yes**. A window opens and you are connected to your instance.

# **Install GitBash**

Once [Git Bash Windows installer](https://git-scm.com/download/win) is downloaded, run the executable file and follow the steps.

![](RackMultipart20230508-1-3vex9c_html_4754d91e7c86b2aa.png)

![](RackMultipart20230508-1-3vex9c_html_d9e74e4a44bcb3b.png)

![](RackMultipart20230508-1-3vex9c_html_570045156d987cba.png)

![](RackMultipart20230508-1-3vex9c_html_a944b862de24c5fb.png)

![](RackMultipart20230508-1-3vex9c_html_d1f2a1470714472e.png)

![](RackMultipart20230508-1-3vex9c_html_4952414646106503.png)

![](RackMultipart20230508-1-3vex9c_html_41998ad4ab87d7d2.png)

![](RackMultipart20230508-1-3vex9c_html_6c483b489199a6f7.png)

![](RackMultipart20230508-1-3vex9c_html_8458ba255ffad6f7.png)

![](RackMultipart20230508-1-3vex9c_html_13b5bf48e18f0fe8.png)

![](RackMultipart20230508-1-3vex9c_html_2b2198fb4be0abc8.png)

![](RackMultipart20230508-1-3vex9c_html_82adb21e9a263d22.png)

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
