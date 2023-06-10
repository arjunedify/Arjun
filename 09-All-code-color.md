# **Git - GitHub**

## **Intro To Version Control System**

- **Version Control** , also known as **revision control** or **source control** ,is the **management of changes** to documents, computer programs, large web sites, and other collections of information.

- Version control allows for the ability to revert a document to a previous version.

![image](https://github.com/arjunedify/Arjun/assets/130965749/323ab169-23cb-4fc0-949b-be822681562e)

- If a mistake is made, developers can turn back the clock and get back the previous working application avoiding disruption, Version control system is critical for allowing editors(developers) to track each other's edits and correct mistakes.

- Changes are usually identified by a number or letter code, termed as the " **revision number**" or " **commit id**".

## **Centralised Version Control System**

##


- Uses a central server to store all files and enables team collaboration.

- But the major drawback of CVCS is its single point of failure, i.e., failure of the central server.

- Unfortunately, if the central server goes down for an hour, then during that hour, no one can collaborate at all.

![image](https://github.com/arjunedify/Arjun/assets/130965749/289046d6-db98-49d8-bea4-70ccd6d30f88)

## **Distributed Version Control System**

- DVCS does not rely on the central server and that is why you can perform many operations when you are offline.

- You can commit changes, create branches and perform other operations when you are offline.

- You require a network connection only to publish your changes and take the latest changes.

![image](https://github.com/arjunedify/Arjun/assets/130965749/dcf6a49f-1b8c-4bec-b03e-1696d89331fc)

## **Git**

## **Git Introduction**

- Git is a Version Control System for tracking changes in computer files and coordinating work on those files among multiple people. It is primarily used for source code management in software development,but it can be used to keep track of changes in any set of files. As a distributed revision control system it is aimed at speed,data integrity and support for distributed workflows.

- Git is a free and open source Distributed Version Control System designed to handle everything from small to very large projects with speed and efficiency. Git is easy to learn and has a tiny footprint with lightning fast performance. It outclasses SCM tools like Subversion, CVS etc

## **Git Architecture**

![image](https://github.com/arjunedify/Arjun/assets/130965749/7a5c2f79-29ff-490e-982d-5f9d437f586a)

## **Git Workflow**

## ![image](https://github.com/arjunedify/Arjun/assets/130965749/5a61a2c0-d878-4268-b361-9d1143cd8d45)

## **Git Branching Model**

### **Branches**

- In a collaborative environment, it is common for several developers to share and work on the same source code.

- Some developers will be fixing bugs while others would be implementing new features. Therefore, there has got to be a **manageable way to maintain different versions of the same code base**.

- This is where the branch function comes to the rescue. **Branch allows each developer to branch out from the original code base and isolate their work from others**. Another good thing about branch is that it helps Git to easily merge the versions later on.

- It is a common practice to create a new branch for each task
  - (eg. bug fixing, new features etc.)

- Branching means you diverge from the main line(master - working copy of application) of development and continue to do work without messing with that main line.

![image](https://github.com/arjunedify/Arjun/assets/130965749/871f08c0-6d48-406c-934c-01c632c0f91e)

![image](https://github.com/arjunedify/Arjun/assets/130965749/e9a8d9a1-29ff-4b3e-94dd-b650bf453df6)

Creating and deleting branches within your repository

- You can create or delete branches directly on GitHub.

Creating a branch

1. On GitHub.com, navigate to the main page of the repository.
2. Optionally, if you want to create your new branch from a branch other than the default branch for the repository, click _NUMBER_ branches then choose another branch:
3. Click the branch selector menu.
4.![image](https://github.com/arjunedify/Arjun/assets/130965749/93dadd58-9baf-4bca-9dc5-2ca1f22100dd)
5. Type a unique name for your new branch, then select Create branch.

##


## **Git Merging Branches**

- The git merge command lets you take the independent lines of development created by the git branch and integrate them into a single branch.

- Git merge will combine multiple sequences of commits into one unified history. In the most frequent use cases, git merge is used to combine two branches.

## **Detached Head for Retro scoping**

![image](https://github.com/arjunedify/Arjun/assets/130965749/f2b3756e-7952-4758-92ab-805393f4f8a0)

## **Undoing Changes**

- Made changes but didn't stage them and commit, use -- checkout
  ```bash
  git checkout -- \<file\>
  ```
- Made changes but staged the changes, use reset
  
  ```bash
  git reset HEAD \<file\>
  ```

- Made changes, staged the changes and commited changes
 ```bash
  - git revert \<commit\>
 ```

## **Git Ignore**

- When sharing your code with others, there are often files or parts of your project you do not want to share.

Examples

log files

temporary files

hidden files

personal files

etc.

Git can specify which files or parts of your project should be ignored by Git using a .gitignore file.

## **GitHub**

## **GitHub For Remote Repositories**

- GitHub, Inc. is a provider of Internet hosting for software development and version control using Git. It offers the distributed version control and source code management functionality of Git, plus its own features.
![image](https://github.com/arjunedify/Arjun/assets/130965749/1e428336-7869-4901-ac36-d1c79dd0af08)

![image](https://github.com/arjunedify/Arjun/assets/130965749/ddcebfc1-6e9d-4765-b04c-23b27f4c4bb5)

## **Using existing GIT Repositories with Clone**

- A repository contains **all of your project's files** and each file's revision history. You can discuss and manage your project's work within the repository.

- You can own repositories individually, or you can share ownership of repositories with other people in an organization.
- The **git clone** command is used to create a copy of a specific repository or branch within a repository.
 ```bash
 git clone \<github-url-repository\>
 ```

## **Pull Requests**

- Pull requests let you tell others about changes you've pushed to a branch in a repository on GitHub. Once a pull request is opened, you can discuss and review the potential changes with collaborators and add follow-up commits before your changes are merged into the base branch.

- After initializing a pull request, you'll see a review page that shows a high-level overview of the changes between your branch (the compare branch) and the repository's base branch.

- After you're happy with the proposed changes, you can merge the pull request. If you're working in a shared repository model, you create a pull request and you, or someone else, will merge your changes from your feature branch into the base branch you specify in your pull request.

### **Creating a repository**

A repository is usually used to organize a single project. Repositories can contain folders and files, images, videos, spreadsheets, and data sets -- anything your project needs. Often, repositories include a README file, a file with information about your project. GitHub makes it easy to add one at the same time you create your new repository. It also offers other common options such as a license file.

Your hello-world repository can be a place where you store ideas, resources, or even share and discuss things with others.

1. In the upper-right corner of any page, use the drop-down menu, and select New repository.
2.![image](https://github.com/arjunedify/Arjun/assets/130965749/631b7c5e-74b9-4c64-99aa-733af8be8e7e)
3. In the Repository name box, enter hello-world.
4. In the Description box, write a short description.
5. Select Add a README file.
6. Click Create repository.
7.![image](https://github.com/arjunedify/Arjun/assets/130965749/cee5737c-33c1-408c-9712-7080ff544297)

###


### **Creating a branch**

Branching lets you have different versions of a repository at one time.

By default, your repository has one branch named main that is considered to be the definitive branch. You can use branches to experiment and make edits before committing them to main.

When you create a branch off the main branch, you're making a copy, or snapshot, of main as it was at that point in time. If someone else made changes to the main branch while you were working on your branch, you could pull in those updates.

This diagram shows:

- The main branch
- A new branch called feature
- The journey that feature takes before it's merged into main

![image](https://github.com/arjunedify/Arjun/assets/130965749/1cea53b2-c589-4eb2-b65b-05f88aa22c37)

Have you ever saved different versions of a file? Something like:

- story.txt
- story-joe-edit.txt
- story-joe-edit-reviewed.txt

Branches accomplish similar goals in GitHub repositories.

Here at GitHub, our developers, writers, and designers use branches for keeping bug fixes and feature work separate from our main (production) branch. When a change is ready, they merge their branch into main.

1. Click the Code tab of your hello-world repository.
2. Click the drop down at the top of the file list that says main.
3. ![image](https://github.com/arjunedify/Arjun/assets/130965749/7fe693ea-9db1-4ec4-9176-a733f90f957e)
4. Type a branch name, readme-edits, into the text box.
5. Click Create branch: readme-edits from main.

![image](https://github.com/arjunedify/Arjun/assets/130965749/d5eea05a-0425-471c-bf95-aeefa3163344)

Now you have two branches, main and readme-edits. Right now, they look exactly the same. Next you'll add changes to the new branch.

### **Making and committing changes**

When you created a new branch in the previous step, GitHub brought you to the code page for your new readme-edits branch, which is a copy of main.

You can make and save changes to the files in your repository. On GitHub, saved changes are called commits. Each commit has an associated commit message, which is a description explaining why a particular change was made. Commit messages capture the history of your changes so that other contributors can understand what you've done and why.

1. Click the README.md file.
2. Click to edit the file.
3. In the editor, write a bit about yourself.
4. In the Commit changes box, write a commit message that describes your changes.
5. Click Commit changes.
6.![image](https://github.com/arjunedify/Arjun/assets/130965749/8e6dedd5-c158-4569-bdc5-8894b0e65a58)

These changes will be made only to the README file on your readme-edits branch, so now this branch contains content that's different from main.

### **Opening a pull request**

Now that you have changes in a branch off of main, you can open a pull request.

Pull requests are the heart of collaboration on GitHub. When you open a pull request, you're proposing your changes and requesting that someone review and pull in your contribution and merge them into their branch. Pull requests show diffs, or differences, of the content from both branches. The changes, additions, and subtractions are shown in different colors.

As soon as you make a commit, you can open a pull request and start a discussion, even before the code is finished.

By using GitHub's @mention feature in your pull request message, you can ask for feedback from specific people or teams, whether they're down the hall or 10 time zones away.

You can even open pull requests in your own repository and merge them yourself. It's a great way to learn the GitHub flow before working on larger projects.

1. Click the Pull requests tab of your hello-world repository.
2. Click New pull request
3. In the Example Comparisons box, select the branch you made, readme-edits, to compare with main (the original).
4. Look over your changes in the diffs on the Compare page, make sure they're what you want to submit.
5. ![](RackMultipart20230610-1-d34f8_html_5f93863b2ef0414d.png)
6. Click Create pull request.
7. Give your pull request a title and write a brief description of your changes. You can include emojis and drag and drop images and gifs.
8. Click Create pull request.

Your collaborators can now review your edits and make suggestions.

### **Merging your pull request**

In this final step, you will merge your readme-edits branch into the main branch.

1. Click Merge pull request to merge the changes into main.
2. Click Confirm merge.
3. Go ahead and delete the branch, since its changes have been incorporated, by clicking Delete branch.

### **Merge Pull Request**

- Merge a pull request into the upstream branch when work is completed. Anyone with push access to the repository can complete the merge.

- In a pull request, you propose that changes you've made on a head branch should be merged into a base branch. By default, any pull request can be merged at any time, unless the head branch is in conflict with the base branch. However, there may be restrictions on when you can merge a pull request into a specific branch. For example, you may only be able to merge a pull request into the default branch if required status checks are passing. For more information, see " **protected branches**."

1. Under your repository name, click Pull requests.
2. ![image](https://github.com/arjunedify/Arjun/assets/130965749/829aa00e-7f7f-42f9-bb89-428db4414adc)
3. In the "Pull Requests" list, click the pull request you'd like to merge.
4. Depending on the merge options enabled for your repository, you can:
  - [Merge all of the commits into the base branch](https://docs.github.com/en/articles/about-pull-request-merges) by clicking Merge pull request. If the Merge pull request option is not shown, then click the merge drop down menu and select Create a merge commit.
  - ![image](https://github.com/arjunedify/Arjun/assets/130965749/9cf25336-26da-4b25-9ad6-6f7a0000decc)

## **Tagging**

- Like most VCSs, Git has the ability to tag specific points in a repository's history as being important. Typically, people use this functionality to mark release points (v1.0, v2.0 and so on). In this section, you'll learn how to list existing tags, how to create and delete tags, and what the different types of tags are.

# **Linux**

## **Intro To Operating Systems**

## **Introduction to Operating Systems Introduction to Linux OS**

- Today, **Linux** runs many of the technologies that power up devices and services. From mobile phones, Google applications, social media networks, to GPS services, Internet of Things (IoT) and Artificial Intelligence (AI) products etc.

- All of the **fastest 500 supercomputers** in the world run on Linux.

- **96.3 percent of the top 1 million web servers** run on Linux OS.

- Since DevOps teams share many responsibilities, A DevOps engineer who knows how to configure/work with linux operating systems and networking technologies, will potentially have few software delivery obstacles.

- Knowing how to work with Linux OS is essential for DevOps to a continual and speedy software delivery process.

##


## **Linux Distributions**

- Typically, Linux is packaged in a form known as a **Linux distribution** (or distro for short) for both desktop [GUI] and **server [CLI]** use.

- Free Distributions are **CentOS** , Amazon Linux, Ubuntu, Debian, openSUSE, etc.,

- Commercial distributions are Red Hat Enterprise Linux, SUSE Linux Enterprise Server, etc.,

##


## **Linux Architecture**

![](RackMultipart20230610-1-d34f8_html_248b2848ea00e1c1.jpg)

- Kernel: Central module(Heart) of OS, interacts with Hardware and responsible for memory management, process management etc.

- Shell : Shell is a command line interpreter i.e, translates commands entered by the user and converts them into a language that is understood by Kernel. Shell is an interface between user and kernel

## **Basics Of Linux**

## **Understanding Command Line Interface - CLI**

- CLI == 100% AUTOMATION

##


## **Understanding Linux File System**

The Linux directory structure is like a tree. The base of the Linux file system hierarchy begins at the **root (/)**. Directories branch off the root, but everything starts at root.

The directory separator in Linux is the forward slash (/). When talking about directories and directory paths, "forward slash" is abbreviated to "slash." Often the root of the file system is referred to as " **slash**" since the full path to it is /.

If you hear someone say "look in slash" or "that file is in slash," they are referring to the root directory.

![](RackMultipart20230610-1-d34f8_html_260d72e7f9e8cd2b.png)

##


## **Using Text Editor (vi)**

The **vi** editor is the most popular and **classic command line text editor** in the Linux family. Below, are some reasons which make it a widely used editor:

- It's pre installed in almost all Linux Distributions i.e centos, ubuntu etc
- It's portable i.e it works the same across different platforms
- It is user-friendly, used by millions of linux users

**Insert Mode**

This mode is for inserting text in the file. You can switch to the Insert mode from the command mode **by pressing 'i' on the keyboard**

Once you are in Insert mode, any key would be taken as an input for the file on which you are currently working. To return to the command mode and save the changes you must press the **esc** key

To launch the vim editor

\> **vi \<new-file\> or \<existing-file\>**

Create a new file named **web.conf** generwally .conf indicates configuration files

\> vi web.conf

To edit the file we need to switch to insert mode **by pressing 'i' on the keyboard** You can tell when you are in insert mode by looking at the bottom left corner.

Now type in a few lines of text and **press esc** which will take you back to edit mode. Command beginning with a colon **( : )** requires you to **hit \<enter\>** to complete the command.

- **:w** - save file but don't exit
- **:wq** - again, save and exit
- **:q!** - discard all changes, and exit

Use **arrow keys** to move the cursor around or use below keys

**h** - left arrow

**l** - right arrow

**j** - down arrow

**k** - up arrow

To go word by word in forward direction - **w**

To go word by 5 words in forward direction - **5w**

To go word by word in backward direction - **b**

To go word by 5 word in backward direction - **5b**

To go beginning of current line - **^** (caret)

To go end of the current line - **$** (dollar)

Page Up - **ctrl + u**

Page Down - **ctrl + d**

Beginning of the File **-**  **gg**

End of the file **-**  **G**

To view the line numbers - **:se nu**

To go to a particular line we use - **30G** (or) **:30**

To hide the line numbers - **:set nonumber**

insert at beginning of the line - **I**

insert at the end of the line - **A**

put text in a new line below the current line - **o**

put text in a new line above current line - **O**

will delete a character for you - **x**

will delete 5 characters deleted - **5x**

delete word - **dw**

delete 4 words - **4dw**

delete line - **dd**

delete 5 lines - **5dd**

delete lines from 3 to 15 - **:3,15dd**

Undo operation - **u**

Redo operation - **cntrl+r**

copy and pastes word - **yw+p**

copy and pastes line - **yy+p**

copies and pastes 5 lines - **5yy+p**

## **File Management With Linux**

## **File & Directory Management**

- File
  - cp \<source-file\> \<dest-path\>
- Directory
  - cp -r \<source-dir\> \<dest-path\>

- The above syntaxes( **cp** ) are for performing local copies, when you want to copy across remote machines we use " **scp**" command

- Copy from Laptop to Remote Server(AWS)
  - scp -i \<pem-key\> \<file-to-copy\> username@\<public-ip-address\>:/path

- Copy from Remote Server(AWS) to Laptop
  - scp -i \<pem-key\> username@\<public-ip-address\>:/path\_server .

- File
  - rm \<source-file\>
- Directory
  - rm -r \<source-dir\>

- Rename
  - mv \<old-file\> \<new-file-name\>

- Move
  - mv \<old-file\> \<dest-directory\>

scp secure copy

scp syntax for laptop to AWS server

scp -i key file\_transfer username@public-IP:~

scp syntax for AWS server to AWS server

scp -i key file\_transfer username@private-IP:~

scp syntax for AWS server to laptop

scp -i key username@public-IP:~/file\_to\_download

## **Archive Files Using tar and zip utilities**

- A Linux tarball ( "tar.gz" or "tar.bz2" file ) is nothing but a system file format that combines and compresses multiple files. Tarballs are common file formats on Linux operating systems. Tarballs are often used for distribution of software/media or backup purposes. This page shows how to tar a file in Linux using the Linux tar command line option.

\> tar cvf FILENAME.tar DIRECTORY/

\> tar xvf FILE.tar

\> zip -r FILE.zip DIRECTORY/

\> unzip FILE.zip

##


## **Package Management**

A software repository, or " repo" for short, is a storage location for software packages.It is a collection of all related files, w.r.t given OS version

\> Yum :: Yellowdog Updater, Modified

sudo apt update

sudo apt list --installed

sudo apt list --installed | grep package

sudo apt list --installed | grep java

sudo apt list --installed | grep python3

Install & Update

sudo apt -y install package

sudo apt -y install elinks

Remove

sudo apt -y remove package

sudo apt -y remove elinks

![](RackMultipart20230610-1-d34f8_html_7aa0ce5346a22593.png)

sudo apt-get install -y mongodb-org

No package mongodb-org available.

[https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/)

By default we have some basic repositories for our use in /etc/apt/sources.list.d/

But to use them:

We need internet

We Need to identify which package we need

##


## **User Management**

Managing users is a critical aspect of server management.

In Ubuntu, the root user is disabled for safety.

Management tasks requiring root access can be completed by using the sudo command by a user who is in the "admin" group.

When you create a user during installation, that user is added automatically to the admin group.

\> sudo adduser username

\> sudo deluser newuser

\> sudo addgroup groupname

\> sudo delgroup groupname

## **File Permissions**

There are three options for permission groups available to you in Linux. These are

owners: these permissions will only apply to owners and will not affect other groups.

groups: you can assign a group of users specific permissions, which will only impact users within the group.

all users: these permissions will apply to all users, and as a result, they present the greatest security risk and should be assigned with caution.

There are three kinds of file permissions in Linux:

Read (r): Allows a user or group to view a file.

Write (w): Permits the user to write or modify a file or directory.

Execute (x): A user or grup with execute permissions can execute a file or view a directory.

The command for changing directory permissions for group owners is similar, but add a "g" for group or "o" for users:

chmod g+w filename

chmod g-wx filename

chmod o+w filename

## **Service Management**

In order to manage the services, you first need to know what services are available on your system.

Combine it with the grep command and you can display just the running services:

\> sudo systemctl | grep running

To start a service in Linux, you just need to use its name like this:

\> systemctl start \<service-name\>

To stop a systemd service, you can use the stop option of systemctl command:

\> systemctl stop \<service-name\>

To restart a service in Linux with systemd, you can use:

\> systemctl restart \<service-name\>

You can confirm that you have successfully executed a certain action by printing the service status:

\> systemctl status \<service-name\>

## **Networking**

## **Understand how IP addresses, ports, and DNS works**

- In networking, a protocol is a set of rules and conventions for formatting and processing data.

- The computers within a network may use vastly different software and hardware; however, the use of protocols enables them to communicate with each other regardless.

![](RackMultipart20230610-1-d34f8_html_de8e89c7986577ce.png)

- Ports are standardized across all network-connected devices, with each port assigned a number. Most ports are reserved for certain protocols — for example, all Hypertext Transfer Protocol (HTTP) messages go to port 80. While IP addresses enable messages to go to and from specific devices, port numbers allow targeting of specific services or applications within those devices.

**What are the different port numbers?**

There are 65,535 possible port numbers, although not all are in common use. Some of the most commonly used ports, along with their associated networking protocol, are:

- **Ports 20 and 21** : File Transfer Protocol (FTP). FTP is for transferring files between a client and a server.
- **Port 22** : Secure Shell (SSH). SSH is one of many tunneling protocols that create secure network connections.
- **Port 25** : Simple Mail Transfer Protocol (SMTP). SMTP is used for email.
- **Port 53** : Domain Name System (DNS). DNS is an essential process for the modern Internet; it matches human-readable domain names to machine-readable IP addresses, enabling users to load websites and applications without memorizing a long list of IP addresses.
- **Port 80** : Hypertext Transfer Protocol (HTTP). HTTP is the protocol that makes the World Wide Web possible.
- **Port 443** : HTTP Secure (HTTPS). HTTPS is the secure and encrypted version of HTTP. All HTTPS web traffic goes to port 443. Network services that use HTTPS for encryption, such as DNS over HTTPS, also connect at this port.
- **Port 3389** : Remote Desktop Protocol (RDP). RDP enables users to remotely connect to their desktop computers from another device.

## **Load Balancers**

- Load balancing is the method of distributing network traffic equally across a pool of resources that support an application.

- Modern applications must process millions of users simultaneously and return the correct text, videos, images, and other data to each user in a fast and reliable manner.

- To handle such high volumes of traffic, most applications have many resource servers with duplicate data between them. A load balancer is a device that sits between the user and the server group and acts as an invisible facilitator, ensuring that all resource servers are used equally.

The simplest configuration for load balancing with nginx may look like the following:

http {

upstream myapp1 {

server srv1.example.com;

server srv2.example.com;

server srv3.example.com;

}

server {

listen 80;

location / {

proxy\_pass http://myapp1;

}

}

}

## **HTTP/HTTPS**

HTTP stands for HyperText Transfer Protocol. It is invented by Tim Berner. HyperText is the type of text which is specially coded with the help of some standard coding language called HyperText Markup Language (HTML). HTTP provides a standard between a web browser and a web server to establish communication. It is a set of rules for transferring data from one computer to another. Data such as text, images, and other multimedia files are shared on the World Wide Web. Whenever a web user opens their web browser, the user indirectly uses HTTP. It is an application protocol that is used for distributed, collaborative, hypermedia information systems.

HTTPS stands for Hyper Text Transfer Protocol Secure. HTTP Secure (HTTPS), could be a combination of the Hypertext Transfer Protocol with the SSL/TLS convention to supply encrypted communication and secure distinguishing proof of an arranged web server. HTTPS is more secure than HTTP because HTTPS is certified by the SSL(Secure Socket Layer). Whatever website you are visiting on the internet, if its URL is HTTP, then that website is not secure.

## **Security**

### **Configure Firewalls to secure the application**

- A firewall can be defined as a special type of network security device or a software program that monitors and filters incoming and outgoing network traffic based on a defined set of security rules.

- The primary purpose of a firewall is to allow non-threatening traffic and prevent malicious or unwanted data traffic for protecting the computer from viruses and attacks.
