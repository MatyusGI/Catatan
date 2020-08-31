# Create project
            composer create-project --prefer-dist laravel/laravel linking_databases

# Create database
Masuk ke database -> mysql -u root -p

Enter password

Buat database -> create database linking_databases;

# Edit .env file
Buka file .env menggunakan vscode 

Ubah :

DB_CONNECTION=mysql

DB_HOST=127.0.0.1

DB_PORT=3306

DB_DATABASE=linking_databases

DB_USERNAME=root

DB_PASSWORD= [your password]

# Make Migration (product)
            php artisan make:migration create_products_table

# Edit migration file
Buka folder database -> migration -> create_products_table.php

Pada function up tambahkan :

            $table->id();
            $table->string('name');
            $table->float('price');
            $table->timestamps();
            

# Make migration (order)
            php artisan make:migration create_orders_table

# Edit migration file
Buka folder database -> migration -> create_orders_table.php

Pada function up tambahkan :

            $table->id();
            $table->foreignId('customer')->constrained('users')->onDelete('cascade')->onUpdate('cascade');  *untuk link database ke tabel users
            $table->dateTime('date_ordered');
            $table->boolean('complete');
            $table->timestamps();
            
# Make migration (order item)
            php artisan make:migration create_orderItems_table

# Edit migration file
Buka folder database -> migration -> create_orders_table.php

Pada function up tambahkan :

            $table->id();
            $table->foreignId('product')->constrained('products')->onDelete('cascade')->onUpdate('cascade');  *untuk link database ke tabel products
            $table->foreignId('order')->constrained('orders')->onDelete('cascade')->onUpdate('cascade');  *untuk link database ke tabel orders
            $table->tinyInteger('quantity');
            $table->dateTime('date_added');
            $table->timestamps();
            
# Migrate
            php artisan migrate

# Make controller & model
            php artisan make:controller ProductController -r -m product

Ketik : yes

# Edit product model
Buka folder app -> product.php

Didalam class product tambahkan :

            protected $fillable = ['name', 'price'];
            
# Install Livewire
Mempermudah dalam JavaScript dan membuat halaman tanpa reload (single page)

            composer require livewire/livewire

# Install Laravel UI
Untuk membuat UI login & register
            composer require laravel/ui
            
# 
