# LAMP-Setup


Steps for LAMP Setup

1. Install Linux(CentOS or RHEL) using VMWare Workstation

2. Install Apache by running following commands in CLI
	a. Switch to root user ```sudo -i```
	b. Install Apache ```yum install httpd```
	c. Stop and disable Firewall using ```systemctl stop firewalld``` and ```systemctl disable firewalld```
	d. Start and enable Apache service using ```systemctl start httpd``` and ```systemctl enable httpd.service```
	e. Check your IP using ```ip a``` and then goto browser and access that IP with port 80 and verify

4. Install MariaDB
	a. Install MariaDB ```yum install mariadb-server```
	b. Start and enable MariaDB service using ```systemctl start mariadb``` and ```systemctl enable mariadb.service```
	c. Use ```mysql_secure_installation``` to setup credentials for MariaDB
	d. Use ```mysql``` to goto DB
	e. Create a new user and grant all privlages by:
```
CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON *.* TO 'newuser'@'localhost';
FLUSH PRIVILEGES;
```
f. Check "SHOW DATABASES;", "CREATE DATABASE NEW_DB;", "USE DATABASE NEW_DB;", "DROP DATABASE NEW_DB;"
	e. exit

6. Install PHP
	a. yum install php php-mysql
	b. systemctl restart httpd.service
	c. Use "vi /var/www/html/info.php" and paste "<?php phpinfo(); ?>" and then verify by "IP/info.php"
