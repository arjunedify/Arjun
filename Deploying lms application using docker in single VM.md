# **Deploying lms application using docker**


![image](https://github.com/arjunedify/Arjun/assets/130965749/571f847d-cfd2-4020-94f5-8f182c2f45e9)

**Installations**

- Ubuntu 20
- git
- docker

**ports to open**
 8080 80 22

**Clone the code**

[https://github.com/digital-lync-2023/lms-public.git](https://github.com/digital-lync-2023/lms-public.git)

![image](https://github.com/arjunedify/Arjun/assets/130965749/7859a8d1-c724-4a28-a147-f8a57b8e0bd7)
switch the branch

 press tab tab to get the branches

 clone the vm-docker-cid branch

write docker files

Create a network

 $ docker network create -d bridge lmsnetwork

# **Creating a database container first**

 $docker run -d -p 5432:5432 --network lmsnetwork -e POSTGRES\_PASSWORD=password --name lmsdb postgres


![image](https://github.com/arjunedify/Arjun/assets/130965749/ea307aaf-0bcc-47bb-a7a7-ed728394dce5)

Building backend image and running backed service

Naviage to backend folder

 $cd api

 $docker build -t mubeen507/lms-backend .

Running a Backend container

$ docker run -d -p 8080:8080 --network lmsnetwork -e DATABASE\_URL=[postgresql://postgres:password@lmsdb:5432/postgres](postgresql://postgres:password@lmsdb:5432/postgres) --name backend -e PORT=8080 -e MODE=local mubeen507/ lms-backend

![image](https://github.com/arjunedify/Arjun/assets/130965749/ebaf4297-1c72-4337-9104-13369abc8907)

Testing backend service is running


 ![image](https://github.com/arjunedify/Arjun/assets/130965749/dd835cd8-7ebe-4ff1-ab29-70862b33a1e1)

# Now configure front end

Add backend url in .env of webapp

 Navigate to web apps folder and create .env file and backend url

![image](https://github.com/arjunedify/Arjun/assets/130965749/6eae1509-b09f-4b29-bbf8-2584f2921a93)

# Now build the front end image


![image](https://github.com/arjunedify/Arjun/assets/130965749/81364a5d-3a4c-4ff7-ab12-8ae216985fc3)

![image](https://github.com/arjunedify/Arjun/assets/130965749/8c58adac-3806-44bf-b67c-5dfcbc186ba2)

Now running the lms-frontend image

 docker run -dt -p 80:80 mubeen507/lms-frontend

![image](https://github.com/arjunedify/Arjun/assets/130965749/f96723c8-9e7f-4be3-8d80-e0f0b073e204)
