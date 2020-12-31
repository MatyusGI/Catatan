# How To Update composer
## cari lokasi binary composer

  '''which composer'''
  
## download composer

  curl -sS https://getcomposer.org/installer -o composer-setup.php
  
jika tidak ada curl install dengan

  sudo apt install curl
  
## install composer

  sudo php composer-setup.php --install-dir=/usr/bin --filename=composer
