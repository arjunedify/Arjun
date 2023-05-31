## **NEXUS ARTIFACTORY**

## **Prerequisites:**

-
## Ubuntu server 20 version .
-
# #Security Group ports open 8081,22,8080.
-
# #Git, Docker, Node, Curl, Wget Tools.

## **Install the Ubuntu server:**

-
## Install Ubuntu server 20 version and take the compute power of t2.medium.
-
## Allow the Security ports of 8081,22,8080.
-
## Launch the instance and login into the server with Bash Terminal with public ip address
![image](https://github.com/arjunedify/Arjun/assets/130965749/4ac624a0-de2f-4fac-8274-cac17f6f0b32)

-
## Clone the Application code from the Github Repository
```
git clone -b vm-docker-cicd https://github.com/digitaledify/lms-public.githt tps://github.com/digitaledify/lms-public.git
```
![image](https://github.com/arjunedify/Arjun/assets/130965749/f2d551f2-8823-40a6-9c15-c9f08be617b5)

- Install node 16 version in the ubuntu machine
```
curl -fsSL https://deb.nodesource.com/setup\_16.x | sudo -E bash - &&sudo apt-get install -y nodejs
```
![image](https://github.com/arjunedify/Arjun/assets/130965749/220db3f1-def9-42ba-84ab-738161e9d0e0)

- Change the directory to the lms-public/webapp
- Build the frontend code with the following build commands
```
sudo npm install
```
```
sudo npm run build
```
- In the lms-public/webapp directory we will get the **dist** file ,which is our build Artifact.

![image](https://github.com/arjunedify/Arjun/assets/130965749/1bdfd63d-06e9-4a7c-ad1c-4341a5706ee4)

# **Install Docker on Ubuntu server:**

- Install Docker on same ubuntu server by visiting the following URL

[
# https://get.docker.com
](https://get.docker.com/)
```
curl -fsSL https://get.docker.com -o install-docker.sh
```
```
sh install-docker.sh --dry-run
```
```
sh install-docker.sh
```
- Docker is installed in the server and add Docker user to the server user
```
sudo useradd -aG docker $user
```
- Run the nexus container by pulling the nexus docker image form the dockerhub by the following command
```
docker run -d -p 8081:8081 --name nexus sonatype/nexus
```
![image](https://github.com/arjunedify/Arjun/assets/130965749/d8cf2373-fea4-4f8c-be56-34531ae4337f)

- Browse the Nexus server by ip-address:8081 in Chrome

![image](https://github.com/arjunedify/Arjun/assets/130965749/33982bdb-f91d-4e1b-b0af-d307cc26f0be)

- Login into the server by admin name and password

![image](https://github.com/arjunedify/Arjun/assets/130965749/4d4bff06-1619-4e23-89e0-b3fc8c0aadf7)

- Default username is admin,Password need to copy from the container which is located in the

/nexus-data/admin.password -c277f4f7-b7c6-4a00-8940-27380b1bc560
```
docker exec -it container id sh
```
```
cat /nexus-data/admin.password
```
![image](https://github.com/arjunedify/Arjun/assets/130965749/e63c08f8-5ca3-4902-88f9-b783e3d1923c)

- Reset the password again with the new password

![image](https://github.com/arjunedify/Arjun/assets/130965749/01b25893-4fff-4f7c-8a53-dfe4923cb575)

- Go to settings and create Repository

![image](https://github.com/arjunedify/Arjun/assets/130965749/0fa13985-03c9-42a1-9a77-da69612907d8)

- Create a Repository of lms-public and select raw hosted option

![image](https://github.com/arjunedify/Arjun/assets/130965749/8c0e90e0-47cc-4b34-8602-3392c5334ac8)

![image](https://github.com/arjunedify/Arjun/assets/130965749/fefd8b28-f85e-4194-9891-4304d341dc92)

- Zip the files which are there in the lms-public/webapp folder

azureuser@Nexus:~/lms-public/webapp$ zip dist.zip dist

- By the above command we will get the zip file of the dist.zip
- From the Server we need to push the Artifact into the Nexus Repository
```
curl -v -u admin:1111111111@yY --upload-file dist.zip http://74.225.248.45:8081/repository/lms-public/
```
admin == username of Nexus login

1111111111@yY == password of Nexus login

![image](https://github.com/arjunedify/Arjun/assets/130965749/90589905-e430-4b0b-b5e4-210771beb2a0)

- The dist.zip file is uploaded into the Nexus Repo

![image](https://github.com/arjunedify/Arjun/assets/130965749/72922a8f-0d43-4ecd-a433-3c2fd0864142)

- To download the files.zip Artifact from the Nexus Repository the following command need to run

![image](https://github.com/arjunedify/Arjun/assets/130965749/8123e184-ff51-49d6-931d-ee4b7b0f4740)
```
wget --user admin --password 1111111111@yY http://74.225.248.45:8081/repository/lms-public/files.zip http://74.225.248.45:8081/repository/lms-public/files.zip
```
```
curl -u admin:Admin123\* -X GET 'http://20.172.187.108:8081/repository/lms/dist-1.1.zip http://20.172.187.108:8081/repository/lms/dist-1.1.zip' --output dist-1.1.zip.
```
admin == username of Nexus login

1111111111@yY == password of Nexus login

NOTE:

Files.zip path:http://74.225.248.45:8081/repository/lms-public/files.zipht tp://74.225.248.45:8081/repository/lms-public/files.zip

![image](https://github.com/arjunedify/Arjun/assets/130965749/79fbebf2-49ec-41f3-9c1f-1488522330d0)

- Finally we uploaded the Artifact from the server to the Nexus Repo
```
curl -v -u admin:1111111111@yY --upload-file dist.zip http://74.225.248.45:8081/repository/lms-public/ http://74.225.248.45:8081/repository/lms-public/
```
- Dowloaded the Articact from the Nexus Repo to the server
```
curl -v -u admin:1111111111@yY --upload-file dist.zip http://74.225.248.45:8081/repository/lms-public/ http://74.225.248.45:8081/repository/lms-public/
```
