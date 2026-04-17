System Update 
sudo apt update

Install Required Packages
sudo apt install apache2 mariadb-server php php-mysqli php-gd php-xml php-mbstring git -y

Start Services
sudo service apache2 start
sudo service mysql start

Navigate to Web Directory
cd /var/www/html

Download DVWA
sudo git clone https://github.com/digininja/DVWA.git

Set Permissions
sudo chmod -R 777 /var/www/html/DVWA

Configure DVWA
cd /var/www/html/DVWA/config
sudo cp config.inc.php.dist config.inc.php
sudo nano config.inc.php

Database Setup
sudo mysql

CREATE DATABASE dvwa;
CREATE USER 'dvwa'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON dvwa.* TO 'dvwa'@'localhost';
FLUSH PRIVILEGES;
EXIT;

Restart Services
sudo service apache2 restart
sudo service mysql restart


check on local host 

SQL Injection Test

1' OR '1'='1
