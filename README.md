# Web-Mail-Server
a web mail server using Roundcube.



# Requirements:
1. Web Server (Apache or Nginx)
2. PHP
3. DBMS
4. Roundcube. download here https://github.com/roundcube/roundcubemail/releases


# Step-by-Step:
1. install all requirements
   - Web Server
     ```
     sudo apt install -y apache2 
     ```
     or if you want to use nginx
     ```
     sudo apt install -y nginx
     ```
   - PHP
     ```
     sudo apt install software-properties-common
     sudo add-apt-repository ppa:ondrej/php
     sudo apt install -y php8.1 libapache2-mod-php8.1
     sudo apt install php-net-ldap2 php-net-ldap3 php-imagick php8.1-common php8.1-gd php8.1-imap php8.1-mysql php8.1-curl php8.1-zip php8.1-xml php8.1-mbstring php8.1-bz2 php8.1-intl php8.1-gmp php8.1-redis
     ```
   - DBMS
     ```
     sudo apt install -y mariadb-server mariadb-client
     ```
     or if you want to use MySQL
     ```
     sudo apt install -y mysql-server
     ```
   - Download Roundcube
     ```
     wget https://github.com/roundcube/roundcubemail/releases/download/1.5.2/roundcubemail-1.5.2-complete.tar.gz
     ```
     you can also use ftp software or use git clone
     
2. create a database
   - enter mysql as a root user
   ```
   sudo mysql -u root
   ```
   - create database, user and password for roundcube. then give all privileges to user
   ```
   CREATE DATABASE <database_name> DEFAULT CHARACTER SET utf8 COLLATE utf8_general_ci;
   CREATE USER <user_name>@localhost IDENTIFIED BY '<user_password>'
   GRANT ALL PRIVILEGES ON <database_name>.* TO <user_name>@localhost;
   FLUSH PRIVILEGES;
   exit;
   ```
3. create virtual host for roundcube
   - create file /etc/<apache2><nginx>/sites-available/<domain_name>.conf
   - to activate domain, use a2ensite
     ```
     a2ensite your_domain.conf
     ```
4. download roundcube use wget
   ```
   wget https://github.com/roundcube/roundcubemail/releases/download/1.5.2/roundcubemail-1.5.2-complete.tar.gz
   ```
   then extract use tar
   ```
   tar xvf roundcubemail-1.5.2-complete.tar.gz
   ```
   move to directory /var/www/roundcube and set owner to www-data for 2 directories. last, import database to file mysql.initial.sql
5. create user for client
   - for create user client, we can make user from vm server
     ```
     adduser <user>
     ```
   - add config for smtp user at config.inc.php, add this line 
     ```
     $config['smtp_user'] = ''
     ```
6. set timezone at php.ini
7. access roundcube domain installer with your browser. http://<yourdomain.com>/installer
8. config database setup, imap setting and smtp setting then press "CREATE CONFIG"
9. remove folder installer at roundcube
10. access again your domain server without /installer

