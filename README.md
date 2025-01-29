# LAMP-Setup


Steps for LAMP Setup

1. Install Linux(CentOS or RHEL) using VMWare Workstation

2. Install Apache by running following commands in CLI
	a. Switch to root user
	b. yum install httpd
	c. systemctl stop firewalld
	d. systemctl disable firewalld
	e. systemctl start httpd
	f. systemctl enable httpd.service
	g. Check your IP using "ip a" and goto browser and access that IP with port 80 and verify by "IP:80"

3. Install MariaDB
	a. yum install mariadb-server
	b. systemctl start mariadb
	c. systemctl enable mariadb.service
	d. Use "mysql_secure_installation" to setup credentials for MariaDB
	e. Use "mysql" to goto DB and create user by "GRANT ALL ON example_database.* TO 'test'@'localhost' IDENTIFIED BY 'PASSWORD' WITH GRANT OPTION;" and "FLUSH PRIVILEGES;"
	f. Check "SHOW DATABASES;", "CREATE DATABASE NEW_DB;", "USE DATABASE NEW_DB;", "DROP DATABASE NEW_DB;"
	e. exit

4. Install PHP
	a. yum install php php-mysql
	b. systemctl restart httpd.service
	c. Use "vi /var/www/html/info.php" and paste "<?php phpinfo(); ?>" and then verify by "IP/info.php"

###############################################################

5. Install Apache Tomcat Tar file
	a. Download zipped tar file from "https://tomcat.apache.org/download-90.cgi#9.0.84" and ftp to your VM
OR	   wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.84/bin/apache-tomcat-9.0.84.zip
	b. gunzip apache-tomcat-9.0.84.zip
	c. tar -xvf apache-tomcat-9.0.84.tar
	d. yum install java-1.8.0-openjdk-devel
	e. "/opt/tomcat/bin/startup.sh" and "/opt/tomcat/bin/shutdown.sh" are configuration files for Tomcat
	f. Verify from browser using "IP:8080"
