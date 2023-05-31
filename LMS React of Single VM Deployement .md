**LMS React on single VM Deployment**

![image](https://github.com/arjunedify/Arjun/assets/132984407/e748c2af-1bb4-45f4-807a-443caf0fb7be)

Source code

VM ubuntu 20

Open ports in security group

22 80 8080 443 5432

![image](https://github.com/arjunedify/Arjun/assets/132984407/ac51505c-c686-4c33-9ebc-a1ee745e42d6)
```
sudo apt install update -y
```
```
sudo apt install upgrade -y
```
```
sudo apt install wget -y
```
```
sudo apt install git -y
```
```
sudo apt install nginx -y
```
```
curl -fsSL https://deb.nodesource.com/setup\_16.x | sudo -E bash - &&sudo apt-get install -y nodejs
```
```
node -v
```
Note : Checkout vm-docker-cicd branch

- Step 1 : First Run the Backend Servers

 Install postgress
```
sudo apt-get -y install postgresql
```
Goto [https://www.postgresql.org/download/linux/ubuntu/](https://www.postgresql.org/download/linux/ubuntu/)

By running the Below 4 commands install the postgress
```
sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb\_release -cs)-pgdg main" \> /etc/apt/sources.list.d/pgdg.list'
```
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
```
sudo apt-get update
```
```
sudo apt-get -y install postgresql
```
![image](https://github.com/arjunedify/Arjun/assets/132984407/0ccd3449-baef-4109-af26-cb5ebe1625fe)

- Once we installed postgress we need to set the password for the postgress
 command to set the password for postgress

Swith user to database user
```
sudo su postgres
```
 

To connect to postgress

postgres@ip-172-31-31-67:/home/ubuntu$ psql
```
  sudo su postgres
```
```
psql
```
![image](https://github.com/arjunedify/Arjun/assets/132984407/585fa37e-2a42-4aef-b241-7b8fcc6a00be)

Set the password using following command

#\password

Setup Backend Setup

- Change the directory to /api

![image](https://github.com/arjunedify/Arjun/assets/132984407/edf48484-8bb7-440d-93ea-5037deed802d)

Navigate to api folder of lms-public /api
 then create .env file in api folder which is our backend source code.

.env file
```
MODE=production

PORT=8080

DATABASE\_URL=postgresql://postgres: **digital** @localhost:5432/postgres
```
![image](https://github.com/arjunedify/Arjun/assets/132984407/ce8b428b-450f-4e98-8015-56d756717cdc)

- And run the below commands to build the code
```
 sudo  npm install
```
```
sudo npm install -g pm2
```
```
sudo  npx prisma db push
```

Now again run the build command as we have done changes in .env file after running npm build new build folder will be generated.
```
sudo npm run build
```
```
NODE\_PORT=8080 pm2 start -i 0 build/index.js
```
![image](https://github.com/arjunedify/Arjun/assets/132984407/5fbae98c-37f2-42ef-8592-d379e56a0425)

Setting port 8080 for backend

# NODE\_PORT=8080 pm2 start -i 0 build/index.js

Now we can check backend connectivity with following command

![image](https://github.com/arjunedify/Arjun/assets/132984407/0c51bc64-664c-476d-b031-3b138cc161da)

You can monitor prisma 2 with command

#pm2 list

#pm2 monit

Now our backing is running up………

Now setting up the FrontEnd


 Prerequisites

- Nginx
- Wget
- Certbot

Navigate frontend code lms-public/webapp

lms-public/webapp #

Now add .env file for front end same as we did for backend


.env file
VITE\_API\_URL value to https://\<backend\_url\>/api

![image](https://github.com/arjunedify/Arjun/assets/132984407/8c3e3306-e70b-4744-b9fd-163c02c62cf6)
![image](https://github.com/arjunedify/Arjun/assets/132984407/702945f5-2e73-41ff-87da-3a24d12014d3)

**My backend url is dev.mubeen.cloud**

Buiding frontend in order to update backend url with frontend

```
 sudo npm install
```


we will get a dist file that is our frontend code … which we are deploying with nginx

![image](https://github.com/arjunedify/Arjun/assets/132984407/69531f2a-1e7b-49f4-ad02-d436edc2927f)

We got the dist file

![image](https://github.com/arjunedify/Arjun/assets/132984407/b8f63c91-5019-498a-a254-856877ebdbbc)

Now we will remove the default config file of nginx
```
sudo rm /etc/nginx/sites-enabled/default
```
```
sudo vi /etc/nginx/sites-available/lms-app
```
```
server {

server\_name [dev.mubeen.cloud](http://www.mubeen.cloud/);

location / {

root /home/ubuntu/lms-public/webapp/dist;

}

location /api {

proxy\_pass http://localhost:8080;

}

}
```
![image](https://github.com/arjunedify/Arjun/assets/132984407/af4793d8-6b34-4fce-8289-50931cd10635)

Now goto DNS provider (godaddy or hostinger etc)

Add A record with ip address
```
sudo ln -s /etc/nginx/sites-available/lms-app /etc/nginx/sites-enabled/lms-app
```
Install CertBot : for https connection

[https://certbot.eff.org/instructions?ws=nginx&os=ubuntufocal](https://certbot.eff.org/instructions?ws=nginx&os=ubuntufocal)
```
sudo snap install core; sudo snap refresh core
```
```
sudo snap install --classic certbot
```
```
sudo ln -s /snap/bin/certbot /usr/bin/certbot
```
```
sudo certbot --nginx
```
```
 sudo nginx -t
```
```
 sudo nginx -s reload
```
![image](https://github.com/arjunedify/Arjun/assets/132984407/71dba6d8-07ca-421d-93f2-d65786b3697f)

History of commands:

1 sudo apt install update -y

2 sudo apt install upgrade -y

3 sudo apt install wget -y

4 sudo apt install git -y

5 sudo apt install nginx -y

7 curl -fsSL https://deb.nodesource.com/setup\_16.x | sudo -E bash - &&sudo apt-get install -y nodejs

8 node -v

9 installed required apps

10 Now cloning the code .........................

11 sudo git clone -b vm-docker-cicd https://github.com/konalms/lms-public.git

12 ls

13 cd lms-public/

14 Installing DATABASE POSTGRES NOW

15 sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb\_release -cs)-pgdg main" \> /etc/apt/sources.list.d/pgdg.list'

16 wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -

17 sudo apt-get -y install postgresql

18 sudo su postgres

19 cd api

20 sudo vi .env

21 MODE=production

22 PORT=8080

23 DATABASE\_URL=postgresql://postgres:digital@localhost:5432/postgres

24 database above url is added in .env file in api folder

26 sudo npm install

27 sudo npm install -g pm2

28 sudo npx prisma db push

29 sudo npm run build

30 NODE\_PORT=8080 pm2 start -i 0 build/index.js

32 curl http://localhost:8080/api

33 backend is up and running -----------

34 Now cd to front end webaapp folder

35 cd ..

36 cd webapp/

37 adding backing url in .env file of frontend directory

38 sudo vi .env

39 adding A Record on DNS ----------------------

40 sudo npm install

41 sudo npm run build

42 sudo rm /etc/nginx/sites-enabled/default

43 sudo vi /etc/nginx/sites-available/lms-app

44 sudo ln -s /etc/nginx/sites-available/lms-app /etc/nginx/sites-enabled/lms-app

45 sudo snap install core; sudo snap refresh core

46 sudo snap install --classic certbot

47 sudo ln -s /snap/bin/certbot /usr/bin/certbot

48 sudo certbot --nginx

49 sudo nginx -t

50 sudo nginx -s reload

51 history
