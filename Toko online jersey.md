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
            
# Make model & migration (Lebih baik jalankan make controller & model)

            php artisan make:model Liga -m
            php artisan make:model Product -m
            php artisan make:model Order -m
            php artisan make:model OrderDetail -m
            
# Make migration

            php artisan make:migration create_ligas_table
            php artisan make:migration create_products_table
            php artisan make:migration create_orders_table
            php artisan make:migration create_order_details_table

# Make controller & model

            php artisan make:controller LigaController -r -m Liga
            php artisan make:controller ProductController -r -m Product
            php artisan make:controller OrderController -r -m Order
            php artisan make:controller OrderDetailController -r -m OrderDetail

# Edit migration
Tambahkan colloum pada table :
## Users
            $table->string('alamat')->nullable();
            $table->string('nohp')->nullable();
## Ligas
            $table->string('nama');
            $table->string('negara');
            $table->string('gambar');
## Products
            $table->string('nama');
            $table->integer('harga')->default(125000);
            $table->integer('harga_nameset')->default(50000);
            $table->integer('liga_id');
            $table->boolean('is_ready')->default(true);
            $table->string('jenis')->default('Replika Top Quality');
            $table->float('berat')->default(0.25);
            $table->string('gambar');
## Orders
            $table->string('kode_pemesanan');
            $table->string('status')->default(0);
            $table->integer('total_harga');
            $table->integer('kode_unik');
            $table->integer('user_id');
## Order_Details
            $table->integer('jumlah_pesanan');
            $table->integer('total_harga');
            $table->boolean('nameset')->default(false);
            $table->string('nama')->nullable();
            $table->string('nomor')->nullable();
            $table->integer('product_id');
            $table->integer('order_id');
            
# Migrate
            php artisan migrate
            
# Make seeder
Digunakan untuk mengisi database

            php artisan make:seeder LigaSeeder
            php artisan make:seeder ProductSeeder
            
# Edit Seeder
Pada folder database -> seeds -> LigaSeeder.php tambahkan :
            
            use Illuminate\Support\Facades\DB;
            
            DB::table('ligas')->insert([
            	'nama' => 'Bundes Liga',
        	            'negara' => 'Jerman',
        	            'gambar' => 'bundesliga.png',
             ]);

            DB::table('ligas')->insert([
        	            'nama' => 'Premier League',
        	            'negara' => 'Inggris',
        	            'gambar' => 'premierleague.png',
            ]);

            DB::table('ligas')->insert([
        	            'nama' => 'La Liga',
        	            'negara' => 'Spanyol',
        	            'gambar' => 'laliga.png',
            ]);

            DB::table('ligas')->insert([
        	            'nama' => 'Serie A',
        	            'negara' => 'Itali',
        	            'gambar' => 'seriea.png',
            ]);
            
Pada folder database -> seeds -> ProductSeeder.php tambahkan :

            use Illuminate\Support\Facades\DB;
            
        DB::table('products')->insert([
        	'nama' => 'CHELSEA 3RD 2018-2019',
            'liga_id' => 2,
            'gambar' => 'chelsea.png'
        ]);

        DB::table('products')->insert([
        	'nama' => 'LEICESTER CITY HOME 2018-2019',
            'liga_id' => 2,
            'gambar' => 'leicester.png'
        ]);

        DB::table('products')->insert([
        	'nama' => 'MAN. UNITED AWAY 2018-2019',
            'liga_id' => 2,
            'gambar' => 'mu.png'
        ]);

        DB::table('products')->insert([
        	'nama' => 'LIVERPOOL AWAY 2018-2019',
            'liga_id' => 2,
            'gambar' => 'liverpool.png'
        ]);

        DB::table('products')->insert([
        	'nama' => 'TOTTENHAM 3RD 2018-2019',
            'liga_id' => 2,
            'gambar' => 'tottenham.png'
        ]);

        DB::table('products')->insert([
        	'nama' => 'DORTMUND AWAY 2018-2019',
            'liga_id' => 1,
            'gambar' => 'dortmund.png'
        ]);

        DB::table('products')->insert([
        	'nama' => 'BAYERN MUNCHEN 3RD 2018 2019',
            'liga_id' => 1,
            'gambar' => 'munchen.png'
        ]);

        DB::table('products')->insert([
        	'nama' => 'JUVENTUS AWAY 2018-2019',
            'liga_id' => 4,
            'gambar' => 'juve.png'
        ]);

        DB::table('products')->insert([
        	'nama' => 'AS ROMA HOME 2018-2019',
            'liga_id' => 4,
            'gambar' => 'asroma.png'
        ]);

        DB::table('products')->insert([
        	'nama' => 'AC MILAN HOME 2018 2019',
            'liga_id' => 4,
            'gambar' => 'acmilan.png'
        ]);

        DB::table('products')->insert([
        	'nama' => 'LAZIO HOME 2018-2019',
            'liga_id' => 4,
            'gambar' => 'lazio.png'
        ]);

        DB::table('products')->insert([
        	'nama' => 'REAL MADRID 3RD 2018-2019',
            'liga_id' => 3,
            'gambar' => 'madrid.png'
        ]);
