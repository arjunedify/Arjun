# **NEXUS ARTIFACTORY**

# **Prerequisites:**

-
# Ubuntu server 20 version .
-
# Security Group ports open 8081,22,8080.
-
# Git, Docker, Node, Curl, Wget Tools.

# **Install the Ubuntu server:**

-
# Install Ubuntu server 20 version and take the compute power of t2.medium.
-
# Allow the Security ports of 8081,22,8080.
-
# Launch the instance and login into the server with Bash Terminal with public ip address

![](RackMultipart20230519-1-25y7b0_html_787fbffc08127557.png)

-
# Clone the Application code from the Github Repository

git clone -b vm-docker-cicd [https://github.com/digitaledify/lms-public.git](https://github.com/digitaledify/lms-public.git)

![](RackMultipart20230519-1-25y7b0_html_9810a984526e7343.png)

- Install node 16 version in the ubuntu machine

curl -fsSL https://deb.nodesource.com/setup\_16.x | sudo -E bash - &&sudo apt-get install -y nodejs

![](RackMultipart20230519-1-25y7b0_html_128ea33c5aa829a5.png)

- Change the directory to the lms-public/webapp
- Build the frontend code with the following build commands

sudo npm install

sudo npm run build

- In the lms-public/webapp directory we will get the **dist** file ,which is our build Artifact.

![](RackMultipart20230519-1-25y7b0_html_53af3641fef9631a.png)

# **Install Docker on Ubuntu server:**

- Install Docker on same ubuntu server by visiting the following URL

[
# https://get.docker.com
](https://get.docker.com/)

curl -fsSL https://get.docker.com -o get-docker.sh

sh get-docker.sh

- Docker is installed in the server and add Docker user to the server user

sudo useradd -aG docker $user

- Run the nexus container by pulling the nexus docker image form the dockerhub by the following command

docker run -d -p 8081:8081 --name nexus sonatype/nexus

![](RackMultipart20230519-1-25y7b0_html_53b108bec508199e.png)

- Browse the Nexus server by ip-address:8081 in Chrome

![](RackMultipart20230519-1-25y7b0_html_f25d5dce1b656794.png)

- Login into the server by admin name and password

![](RackMultipart20230519-1-25y7b0_html_cbd003548122a9da.png)

- Default username is admin,Password need to copy from the container which is located in the

/nexus-data/admin.password -c277f4f7-b7c6-4a00-8940-27380b1bc560

docker exec -it container id sh

cat/nexus-data/admin.password

![](RackMultipart20230519-1-25y7b0_html_51e0f27d5e83338.png)

- Reset the password again with the new password

![](RackMultipart20230519-1-25y7b0_html_596da0f4b7febade.png)

- Go to settings and create Repository

![](RackMultipart20230519-1-25y7b0_html_9afca3172cf58752.png)

- Create a Repository of lms-public and select raw hosted option

![](RackMultipart20230519-1-25y7b0_html_1dc9febb48b2dedb.png)

![](RackMultipart20230519-1-25y7b0_html_51ef5a30bd7d4e4.png)

- Zip the files which are there in the lms-public/webapp folder

azureuser@Nexus:~/lms-public/webapp$ zip dist.zip dist

- By the above command we will get the zip file of the dist.zip
- From the Server we need to push the Artifact into the Nexus Repository

curl -v -u admin:1111111111@yY --upload-file dist.zip [http://74.225.248.45:8081/repository/lms-public/](http://74.225.248.45:8081/repository/lms-public/)

admin == username of Nexus login

1111111111@yY == password of Nexus login

![](RackMultipart20230519-1-25y7b0_html_5c18f9fc8c697d7a.png)

- The dist.zip file is uploaded into the Nexus Repo

![](RackMultipart20230519-1-25y7b0_html_729bbbcd4d78bb72.png)

- To download the files.zip Artifact from the Nexus Repository the following command need to run

![](RackMultipart20230519-1-25y7b0_html_ec774d138916ce2.png)

wget --user admin --password 1111111111@yY [http://74.225.248.45:8081/repository/lms-public/files.zip](http://74.225.248.45:8081/repository/lms-public/files.zip)

curl -u admin:Admin123\* -X GET '[http://20.172.187.108:8081/repository/lms/dist-1.1.zip](http://20.172.187.108:8081/repository/lms/dist-1.1.zip)' --output dist-1.1.zip.

admin == username of Nexus login

1111111111@yY == password of Nexus login

NOTE:

Files.zip path:[http://74.225.248.45:8081/repository/lms-public/files.zip](http://74.225.248.45:8081/repository/lms-public/files.zip)

![](RackMultipart20230519-1-25y7b0_html_9bad901a6bad31c6.png)

- Finally we uploaded the Artifact from the server to the Nexus Repo

curl -v -u admin:1111111111@yY --upload-file dist.zip [http://74.225.248.45:8081/repository/lms-public/](http://74.225.248.45:8081/repository/lms-public/)

- Dowloaded the Articact from the Nexus Repo to the server

curl -v -u admin:1111111111@yY --upload-file dist.zip [http://74.225.248.45:8081/repository/lms-public/](http://74.225.248.45:8081/repository/lms-public/)
