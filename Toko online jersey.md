# Create project
            composer create-project --prefer-dist laravel/laravel jersey

# Create database
Masuk ke database -> mysql -u root -p

Enter password

Buat database -> create database jersey;

# Edit .env file
Buka file .env menggunakan vscode 

Ubah :

DB_CONNECTION=mysql

DB_HOST=127.0.0.1

DB_PORT=3306

DB_DATABASE=jersey

DB_USERNAME=root

DB_PASSWORD= [your password]


# Install Livewire
Mempermudah dalam JavaScript dan membuat halaman tanpa reload (single page)

            composer require livewire/livewire

# Install Laravel UI
Untuk membuat UI login & register

            composer require laravel/ui
            
# Make authentication
Membuat halaman login & register

            php artisan ui bootstrap --auth
            
# Install Turbolinks
Untuk membuat single page

            npm install --save turbolinks
            npm install && npm run dev
            
Buka folder resources -> js -> app.js

Didalam app.js tambahkan :
            
            var Turbolinks = require("turbolinks")
            Turbolinks.start()

Lakukan lagi :

            npm install && npm run dev

Buka folder resources -> views -> layuots -> app.blade.php

Didalam app.blade.php bagian head tambahkan :

            <livewire:styles/>
            <livewire:scripts/>

# Mengubah nama web
Buka file .env ubah :

            APP_NAME=E-shop
            
# Make migration & model
            php artisan make:model liga -m
            
