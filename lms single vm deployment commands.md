```bash
sudo apt-get update -y
```

Installling postgress
```bash
sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb\_release -cs)-pgdg main" \> /etc/apt/sources.list.d/pgdg.list'
```
```bash
sudo apt install wget -y
```
```bash
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
```
```bash
sudo apt-get -y install postgresql
```
```bash
sudo systemctl status postgresql
```
```bash
sudo systemctl enable postgresql
```
```bash
sudo su - postgres
```
```bash
cd lms-public/
```

End of postgress

Now configuring backend tht is api
```bash
cd api/
```
installing node
```bash
curl -fsSL https://deb.nodesource.com/setup\_16.x | sudo -E bash -
```
```bash
sudo apt-get install -y nodejs
```
```bash
node -v
```
```bash
npm -v
```
```bash
sudo vi .env
```
```bash
npm install
```
```bash
sudo npm install -g pm2
```
```bash
sudo npx prisma db push
```
Now setting up frontend
```bash
cd ..
```
```bash
cd webapp/
```
```bash
sudo apt install nginx -y
```
```bash
sudo vi .env
```
```bash
curl http://3.101.23.98:8080/api
```
```bash
npm install
```
```bash
sudo rm /var/www/html/index.nginx-debian.html
```
 
