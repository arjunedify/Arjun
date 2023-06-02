sudo apt-get update -y

Installling postgress

sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb\_release -cs)-pgdg main" \> /etc/apt/sources.list.d/pgdg.list'

sudo apt install wget -y

wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -

sudo apt-get -y install postgresql

sudo systemctl status postgresql

sudo systemctl enable postgresql

sudo su - postgres

cd lms-public/

End of postgress

Now configuring backend tht is api

cd api/

installing node

curl -fsSL https://deb.nodesource.com/setup\_16.x | sudo -E bash -

sudo apt-get install -y nodejs

node -v

npm -v

sudo vi .env

npm install

sudo npm install -g pm2

sudo npx prisma db push

Now setting up frontend

cd ..

cd webapp/

sudo apt install nginx -y

sudo vi .env

curl http://3.101.23.98:8080/api

npm install

sudo rm /var/www/html/index.nginx-debian.html

lms single vm deployment commands
