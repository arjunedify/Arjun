# **Deploying lms application using docker**


 ![](RackMultipart20230515-1-js5oue_html_e42fb2b3dd65e9fa.jpg)

**Installations**

- Ubuntu 20
- git
- docker

**ports to open**
 8080 80 22

**Clone the code**

[https://github.com/digital-lync-2023/lms-public.git](https://github.com/digital-lync-2023/lms-public.git)

![](RackMultipart20230515-1-js5oue_html_4c0e14c53e37bcc3.png)
switch the branch

 press tab tab to get the branches

 clone the vm-docker-cid branch

write docker files

Create a network

 $ docker network create -d bridge lmsnetwork

# **Creating a database container first**

 $docker run -d -p 5432:5432 --network lmsnetwork -e POSTGRES\_PASSWORD=password --name lmsdb postgres


 ![](RackMultipart20230515-1-js5oue_html_170733c1b6b6f083.png)

Building backend image and running backed service

Naviage to backend folder

 $cd api

 $docker build -t mubeen507/lms-backend .

Running a Backend container

$ docker run -d -p 8080:8080 --network lmsnetwork -e DATABASE\_URL=[postgresql://postgres:password@lmsdb:5432/postgres](postgresql://postgres:password@lmsdb:5432/postgres) --name backend -e PORT=8080 -e MODE=local mubeen507/ lms-backend

![](RackMultipart20230515-1-js5oue_html_c86b5fba74ab4ed6.png)

Testing backend service is running


 ![](RackMultipart20230515-1-js5oue_html_8695adeb17d93fa2.png)

# Now configure front end

Add backend url in .env of webapp

 Navigate to web apps folder and create .env file and backend url


 ![](RackMultipart20230515-1-js5oue_html_33c630a3640bdc0.png)

# Now build the front end image


![](RackMultipart20230515-1-js5oue_html_3bae0376bc6484ed.png)

![](RackMultipart20230515-1-js5oue_html_86982ec4f324021d.png)

Now running the lms-frontend image

 docker run -dt -p 80:80 mubeen507/lms-frontend

![](RackMultipart20230515-1-js5oue_html_e749fdfb562f0d86.png)
