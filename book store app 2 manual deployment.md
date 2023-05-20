Task book store App

Front end : PHP

Database : Mysql

Soltuion:

Take 2 ec2 instances

1. For App Server .. PHP code
2. Database : Mysql server

Solution :

# Install mysql

sudo yum install update

wget http://repo.mysql.com/mysql-community-release-el7-5.noarch.rpm

sudo rpm -ivh mysql-community-release-el7-5.noarch.rpm

yum install mysql-community-server -y

service mysqld status

service mysqld start

## To connect to mysql server localy in same pc

$sudo mysql\_secure\_installation

To from every where we need to give permission for mysql and create user for remote

CREATE USER 'useremote'@'%' IDENTIFIED BY 'Urpassword@123';
GRANT ALL ON \*.\* TO 'remote'@'%';

To connect to database

$mysql -u root -p

Now Creating the Table

[https://github.com/mubeen507/php-lamp](https://github.com/mubeen507/php-lamp)

for file/php/db.php

CREATE DATABASE bookstore;

use bookstore;

CREATE TABLE books(id INT(11) NOT NULL AUTO\_INCREMENT PRIMARY KEY,book\_name VARCHAR (25) NOT NULL, book\_publisher VARCHAR (20),book\_price FLOAT);

![image](https://github.com/arjunedify/Arjun/assets/130965749/77b7d98d-9cca-4eaf-80d1-3dd76ae169e0)
select database bookstore

$ use bookstore;

Will display database changed

$ show tables;
![image](https://github.com/arjunedify/Arjun/assets/130965749/6875647a-4bc4-4a44-b21c-77a8b16d4056)

Now the database and tables are ready

Goto app server and update the /src/db.php file with db name user name password and location of mysql database installed server ip as shown below.

![image](https://github.com/arjunedify/Arjun/assets/130965749/2883f462-e327-45d1-b4a8-6207bc627525)

Now in app server

Install php and my httpd server

$ yum install httpd -y

$sudo yum install epel-release yum-utils -y

$sudo yum install http://rpms.remirepo.net/enterprise/remi-release-7.rpm -y

$sudo yum-config-manager --enable remi-php73

$sudo yum install php php-common php-opcache php-mcrypt php-cli php-gd php-curl php-mysqlnd -y

$php -version

$

$sudo yum install httpd

To check connectivity from app server to mysql server

$sudo yum install mysql

$ mysql -h 44.202.127.115 -u remote -p

Enter password

If u get sql \>
