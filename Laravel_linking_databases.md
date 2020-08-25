# Create project
composer create-project --prefer-dist laravel/laravel linking_databases

# Create database
masuk ke database -> mysql -u root -p

enter password

buat database -> create database linking_databases;

# Edit .env file
buka file .env menggunakan vscode 

ubah :

DB_CONNECTION=mysql

DB_HOST=127.0.0.1

DB_PORT=3306

DB_DATABASE=linking_databases

DB_USERNAME=root

DB_PASSWORD= [your password]

# Make Migration (product)
php artisan make:migration create_products_table

# Edit migration file
buka folder database -> migration -> create_products_table.php

pada function up tambahkan :

            $table->id();
            
            $table->string('name');
            
            $table->float('price');
            
            $table->timestamps();
            

# Make migration (order)
php artisan make:migration create_orders_table

# Edit migration file
buka folder database -> migration -> create_orders_table.php

pada function up tambahkan :

            $table->id();
            
            $table->foreignId('customer')->constrained('users')->onDelete('cascade')->onUpdate('cascade');  *untuk link database ke tabel users
            
            $table->dateTime('date_ordered');
            
            $table->boolean('complete');
            
            $table->timestamps();
            
# Make migration (order item)
php artisan make:migration create_orderItems_table

# Edit migration file
buka folder database -> migration -> create_orders_table.php

pada function up tambahkan :

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

yes

# Edit product model
buka folder app -> product.php

didalam class product tambahkan :

            protected $fillable = ['name', 'price'];
            
# 
