    1  sudo apt-get update -y
    2  Installling postgress
    3  sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
    4  sudo apt install wget -y
    5  wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
    6  sudo apt-get -y install postgresql
    7  sudo systemctl status postgresql
    8  sudo systemctl enable postgresql
    9  sudo su - postgres
   10  cd lms-public/
   11  End  of postgress
   12  Now configuring backend tht is api
   13  cd api/
   14  installing node
   15  curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash -
   16  sudo apt-get install -y nodejs
   17  node -v
   18  npm -v
   19  sudo vi .env
   20  npm install
   21  sudo npm install -g pm2
   22  sudo  npx prisma db push
   23  Now setting up frontend
   24  cd ..
   25  cd webapp/
   26  sudo apt install nginx -y
   27  sudo vi .env
   28  curl http://3.101.23.98:8080/api
   29  npm install
   30  sudo rm /var/www/html/index.nginx-debian.html

