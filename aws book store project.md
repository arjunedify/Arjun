![](RackMultipart20230519-1-joxtyf_html_a00a6c1b8502d056.png)

Repo link

[https://github.com/mubeen507/php-lamp](https://github.com/mubeen507/php-lamp)

Commands

Installing mysql 5.6

sudo yum install update

sudo yum install wget git httpd -y

sudo setenforce 0

sudo git clone https://github.com/mubeen507/php-lamp /var/www/html

Instaling php

sudo yum install php

JDBC mysql connection

sudo yum install -y php-mysql

wget http://repo.mysql.com/mysql-community-release-el7-5.noarch.rpm

sudo rpm -ivh mysql-community-release-el7-5.noarch.rpm

sudo yum install mysql-community-server -y

sudo service mysqld status

sudo service mysqld start

Configuration mysqldb

sudo mysql\_secure\_installation

connecting to mysqldb or login to datatbase

mysql -u root -p

Creating dabase

CREATE DATABASE bookstore;

use bookstore;

CREATE TABLE books(id INT(11) NOT NULL AUTO\_INCREMENT PRIMARY KEY,book\_name VARCHAR (25) NOT NULL, book\_publisher VARCHAR (20),book\_price FLOAT);

show tables;

desc books;

assiging permission to sql

SHOW GRANTS FOR root;

GRANT ALL PRIVILEGES ON bookstore.\* TO 'root'@'localhost';

select \* from books;

\_\_\_\_\_\_\_\_\_\_\_end\_\_\_\_\_\_\_\_\_\_\_\_
