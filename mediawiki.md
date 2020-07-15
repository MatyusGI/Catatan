# set locale
sudo locale-gen id_ID.UTF-8

# update repo
sudo apt update

sudo su

# install apache2
apt -y install apache2

sudo ufw allow 'Apache'

# install PHP 7.4
sudo apt -y install software-properties-common

sudo add-apt-repository ppa:ondrej/php

sudo apt update

sudo apt -y install php7.4

## install extension
sudo apt -y install php7.4-common php7.4-mysql php7.4-xml php7.4-xmlrpc \
php7.4-curl php7.4-gd php7.4-imagick php7.4-cli php7.4-dev \
php7.4-imap php7.4-mbstring php7.4-opcache php7.4-soap \
php7.4-zip php7.4-cli php7.4-intl \
imagemagick git zip libgd-dev libapache2-mod-php 

## edit
sudo vim /etc/php/7.4/apache2/php.ini

upload_max_filesize = 100M

post_max_size = 48M

memory_limit = 512M

max_execution_time = 600

max_input_vars = 3000

max_input_time = 1000

## restart apache2
sudo systemctl restart apache2.service

# install percona
wget https://repo.percona.com/apt/percona-release_latest.$(lsb_release -sc)_all.deb

sudo dpkg -i percona-release_latest.$(lsb_release -sc)_all.deb

sudo percona-release setup ps57

sudo apt -y install percona-server-server-5.7

## edit
sudo vim /etc/mysql/percona-server.conf.d/mysqld.cnf

[mysqld]

max_allowed_packet=32M (ditambahkan setelah explicit_defaults_for_timestamp)

# setup database
mysql -u root -p

Enter password:

create database mediawiki;

GRANT SELECT,INSERT,UPDATE,DELETE,CREATE,CREATE TEMPORARY TABLES,DROP,INDEX,ALTER ON mediawiki.* TO mediawiki@localhost IDENTIFIED BY 'yourpassword';

exit

/etc/init.d/mysql restart

# install mediawiki
cd /usr/local/src

wget https://releases.wikimedia.org/mediawiki/1.32/mediawiki-1.32.0.tar.gz

cp mediawiki-1.32.0.tar.gz /var/www/html/

cd /var/www/html/

tar zxvf mediawiki-1.32.0.tar.gz

mv mediawiki-1.32.0 wiki

cp -Rf /var/www/html/wiki/mw-config/ /var/www/html/wiki/config

chmod a+w /var/www/html/wiki/mw-config

chmod a+w /var/www/html/wiki/config

chmod -Rf 777 wiki

chown -Rf www-data.www-data wiki

# restart apache
/etc/init.d/apache2 restart

# Selesaikan Konfigurasi Mediawiki
http://localhost/wiki

http://ip-address-server/wiki

# Versi 1.17 ke atas
Your language: id

Wiki language: id -> lanjut

Pengecekan Lingkungan > lanjut

Pengaturan MySQL


  Inang basis data: localhost
  
  Nama basis data: mediawiki
  
  Prefiks tabel basis data: wiki_
  
  Nama pengguna basis data: mediawiki
  
  Kata sandi basis data: mediawiki -> lanjut
  

Mesin penyimpanan: InnoDB

Set karakter basis data: Biner -> lanjut


Nama wiki:

Nama Anda:

Kata sandi:

Kata sandi lagi:

Alamat surel:

Saya sudah bosan, instal saja wikinya. -> lanjut


Instal -> lanjut

download localsettings.php

copy file dengan menggunakan winscp ke /var/ww/html/wiki

mediawiki dapat dijalankan
