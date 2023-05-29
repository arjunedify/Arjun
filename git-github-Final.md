
**Version Control:**

**Version Control** , also known as **revision control** or **source control** ,

Version control is a system that helps to keep track of changes made to a set of files or code over time. It allows multiple people to work on the same set of files without overwriting each other's changes.

version control is like a time machine that keeps a record of every change made to a file or set of files. This means that you can easily go back in time to a previous version of a file, compare different versions, and see who made what changes and when. It is commonly used by software developers, but it can also be used for any type of document or file that undergoes multiple revisions.

![image](https://user-images.githubusercontent.com/130965749/236376146-b8f26d93-29b8-4fcf-a531-ef5608ff2dde.png)

- Version control allows for the ability to revert a document to a previous version.

![image](https://user-images.githubusercontent.com/130965749/236376180-0e0faa19-a409-4823-839d-2b22c00c59a9.png)
![image](https://user-images.githubusercontent.com/130965749/236376210-530a37f6-c487-4752-a91f-2f98c903d52f.png)

**Centralized Version Control System**

![image](https://user-images.githubusercontent.com/130965749/236376252-67a054ee-5035-4f56-8e42-b7e3dd5f701e.png)

![image](https://user-images.githubusercontent.com/130965749/236376284-262c7aab-4f16-4736-a0f8-aaba53c5fdf5.png)

**Distributed Version Control System**

![image](https://user-images.githubusercontent.com/130965749/236376313-932af1ad-a359-4bc8-b378-4fb73bd9d679.png)

![image](https://user-images.githubusercontent.com/130965749/236376342-210bba91-a9cb-4b3b-83d3-e3e87271dc8c.png)

**WHAT IS GIT**

Git is a free and open-source version control system that helps developers to manage and track changes in their code over time

Git is like a tool that allows developers to keep track of the changes they make to their code over time. It keeps a record of every change made to a file, allowing developers to easily undo changes or go back to an earlier version of their code. Git also allows multiple developers to work on the same project at the same time without interfering with each other's work.

**What is GITHUB ?**

GitHub is a web-based platform that allows developers to store and share their code with others. It is built on top of Git

It provides a central place to store and manage code repositories, and offers tools for version control, bug tracking, code review

![image](https://user-images.githubusercontent.com/130965749/236376393-3181e5ae-2ae3-4542-ac02-78a90b607b2c.png)

Repository is like a folder or directory that contains all the files and code related to a project, along with a record of every change made to those file

## **GIT WORKFLOW:**

![image](https://user-images.githubusercontent.com/130965749/236376422-aebd09d5-ffe8-4e5a-916b-ae2f49fc86a6.png)

**GIT Commands:**

- The **git add** command - adds a change in the working directory to the staging area. It tells Git that you want to include updates to a particular file in the next commit.

- The **git commit** command - creates a commit, which is like a snapshot of your repository. These commits are snapshots of your entire repository at specific times. You should make new commits often, based around logical units of change. Over time, commits should tell a story of the history of your repository and how it came to be the way that it currently is. Commits include lots of metadata in addition to the contents and message, like the author, timestamp, and more.
  - git commit -m "descriptive commit message"

- The **git push** command - The git push command is used to upload local repository content to a remote repository. Pushing is how you transfer commits from your local repository to a remote repo.
```
git config --global user.name "kona"
 
```
```
git config --global user.email "kona@konalms.com"
```
```
git status
```
```
git --version
```
```
git add
```
```
git commit -m "Message"
```
```
git status
```
```
git config --list
```
```
git pull
```
```
git push
```
```
git remote set-url origin git@github.com:digital-edify/lms-public.git
```

## **BRANCHES**

**Git Branching**

- In a collaborative environment, it is common for several developers to share and work on the same source code.

- Some developers will be fixing bugs while others would be implementing new features. Therefore, there has got to be a **manageable way to maintain different versions of the same code base**.

- This is where the branch function comes to the rescue. **Branch allows each developer to branch out from the original code base and isolate their work from others**. Another good thing about branch is that it helps Git to easily merge the versions later on.

- It is a common practice to create a new branch for each task
  - (eg. bug fixing, new features etc.)

- Branching means you diverge from the main line(master - working copy of application) of development and continue to do work without messing with that main line.

![image](https://user-images.githubusercontent.com/130965749/236376467-05ca88ff-9c0b-4588-a6b8-aa6aea8c25ca.png)

![image](https://user-images.githubusercontent.com/130965749/236376492-9197b5ac-150e-4cc4-ad39-9976558aeb98.png)

Git is maintained by Linux.

Github is maintained by Microsoft.

Git is a command-line tool.

Github is a graphical user Interface.

Git is a Software

Github is a Service

Git was released in 2005.

Github was launched in 2008.

Git is Installed locally on the system.

Github is hosted on the web.

Git has no user management feature.

Github has built-in user management feature.

Git can manage source code history.

Github is a hosting service for git repositories.

Git is focused on version control & code sharing

Github is focused on centralized source code hosting
