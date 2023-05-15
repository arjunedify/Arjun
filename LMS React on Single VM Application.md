**LMS React on single VM Deployment**

![](RackMultipart20230515-1-83mpc7_html_31537c04304d83fa.png)

Source code

VM ubuntu 20

Open ports in security group

22 80 8080 443 5432

![](RackMultipart20230515-1-83mpc7_html_f317a508a7f44883.png)

sudo apt install update -y

sudo apt install upgrade -y

sudo apt install wget -y

sudo apt install git -y

sudo apt install nginx -y

curl -fsSL https://deb.nodesource.com/setup\_16.x | sudo -E bash - &&sudo apt-get install -y nodejs

node -v

Note : Checkout vm-docker-cicd branch

- Step 1 : First Run the Backend Servers

 Install postgress

sudo apt-get -y install postgresql

Goto [https://www.postgresql.org/download/linux/ubuntu/](https://www.postgresql.org/download/linux/ubuntu/)

By running the Below 4 commands install the postgress

sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb\_release -cs)-pgdg main" \> /etc/apt/sources.list.d/pgdg.list'

wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -

sudo apt-get update

sudo apt-get -y install postgresql

![](RackMultipart20230515-1-83mpc7_html_245e172e0425f524.png)

- Once we installed postgress we need to set the password for the postgress
 command to set the password for postgress

Swith user to database user

sudo su postgres

sudo su postgres

To connect to postgress

postgres@ip-172-31-31-67:/home/ubuntu$ psql

  #sudo su postgres

#psql

![](RackMultipart20230515-1-83mpc7_html_e3a4db7ff48e7219.png)

Set the password using following command

#\password

Setup Backend Setup

- Change the directory to /api

![](RackMultipart20230515-1-83mpc7_html_61dd63a83f0d0f8a.png)

Navigate to api folder of lms-public /api
 then create .env file in api folder which is our backend source code.

.env file

MODE=production

PORT=8080

DATABASE\_URL=postgresql://postgres: **digital** @localhost:5432/postgres

![](RackMultipart20230515-1-83mpc7_html_627e9a72c7513b1e.png)

- And run the below commands to build the code

 #sudo  npm install

# sudo npm install -g pm2

#sudo  npx prisma db push

Now again run the build command as we have done changes in .env file after running npm build new build folder will be generated.

sudo npm run build

NODE\_PORT=8080 pm2 start -i 0 build/index.js

![](RackMultipart20230515-1-83mpc7_html_a2edce22d1e9e428.png)

Setting port 8080 for backend

# NODE\_PORT=8080 pm2 start -i 0 build/index.js

Now we can check backend connectivity with following command

![](RackMultipart20230515-1-83mpc7_html_133bc094629bffa7.png)

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

![](RackMultipart20230515-1-83mpc7_html_eb431e791da5b70a.png)

![](RackMultipart20230515-1-83mpc7_html_bbcfa88f50f92e4b.png)

**My backend url is dev.mubeen.cloud**

Buiding frontend in order to update backend url with frontend


 sudo npm install

d

we will get a dist file that is our frontend code … which we are deploying with nginx

![](RackMultipart20230515-1-83mpc7_html_f7f3570062f00a72.png)

We got the dist file

![](RackMultipart20230515-1-83mpc7_html_8164ad41a29269da.png)

Now we will remove the default config file of nginx

#sudo rm /etc/nginx/sites-enabled/default

#sudo vi /etc/nginx/sites-available/lms-app

server {

server\_name [dev.mubeen.cloud](http://www.mubeen.cloud/);

location / {

root /home/ubuntu/lms-public/webapp/dist;

}

location /api {

proxy\_pass http://localhost:8080;

}

}

![](RackMultipart20230515-1-83mpc7_html_c81065fddb1ee8a0.png)

Now goto DNS provider (godaddy or hostinger etc)

Add A record with ip address

sudo ln -s /etc/nginx/sites-available/lms-app /etc/nginx/sites-enabled/lms-app

Install CertBot : for https connection

[https://certbot.eff.org/instructions?ws=nginx&os=ubuntufocal](https://certbot.eff.org/instructions?ws=nginx&os=ubuntufocal)

sudo snap install core; sudo snap refresh core

sudo snap install --classic certbot

sudo ln -s /snap/bin/certbot /usr/bin/certbot

sudo certbot --nginx

 sudo nginx -t

 sudo nginx -s reload

![](RackMultipart20230515-1-83mpc7_html_5618cb58268a274a.png)

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

