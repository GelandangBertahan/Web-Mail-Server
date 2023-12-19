# Web-Mail-Server
a web mail server using Roundcube.



# Requirements:
1. Web Server (Apache or Nginx)
2. PHP
3. Databases
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
   - Databases
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
     
