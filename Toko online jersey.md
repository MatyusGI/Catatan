# Create project
            composer create-project --prefer-dist laravel/laravel jersey

# Create database
Masuk ke database -> mysql -u root -p

Enter password

Buat database -> create database jersey;

# Edit .env file
Buka file .env menggunakan vscode. 

Ubah :

DB_CONNECTION=mysql

DB_HOST=127.0.0.1

DB_PORT=3306

DB_DATABASE=jersey

DB_USERNAME=root

DB_PASSWORD= [your password]


# Install Livewire
Mempermudah dalam JavaScript dan membuat halaman tanpa reload (single page).

            composer require livewire/livewire

# Install Laravel UI
Untuk membuat UI login & register.

            composer require laravel/ui
            
# Make authentication
Membuat halaman login & register.

            php artisan ui bootstrap --auth
            
# Install Turbolinks
Untuk membuat single page.

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
Digunakan untuk mengisi database.

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

# Seeding database
Mengisi otomatis database menggunakan seeder.

            php artisan db:seed --class=LigaSeeder
            php artisan db:seed --class=ProductSeeder
            
# Linking database
Pada folder app -> Liga.php tambahkan :

    public function products()
    {
        return $this->hasMany(Product::class, 'liga_id', 'id');
    }
            
Pada folder app -> Order.php tambahkan :

    public function order_details()
    {
        return $this->hasMany(OrderDetail::class, 'order_id', 'id');
    }

    public function user()
    {
        return $this->belongsTo(User::class, 'user_id', 'id');
    }
            
Pada folder app -> OrderDetails.php tambahkan :

    public function order()
    {
        return $this->belongsTo(Order::class, 'order_id', 'id');
    }

    public function product()
    {
        return $this->belongsTo(Product::class, 'product_id', 'id');
    }
            
Pada folder app -> Product.php tambahkan :

    public function liga()
    {
        return $this->belongsTo(Liga::class, 'liga_id', 'id');
    }

    public function order_details()
    {
        return $this->hasMany(OrderDetail::class, 'product_id', 'id');
    }
            
Pada folder app -> User.php tambahkan :

    public function orders()
    {
        return $this->hasMany(Order::class, 'user_id', 'id');
    }

# Download Images
Download dari : https://drive.google.com/drive/folders/18bVutvyCrAltWPIQHoNRAEKJUwVF9CfK

Pindahkan ke folder (nama project laravel) -> public -> (paste didalam folder public)

# Create a component livewire
Membuat halaman home dengan livewire.

            php artisan make:livewire Home
            php artisan make:livewire Navbar
            
# Edit route
Pada Route -> web.php ubah menjadi :

            Auth::routes();

            Route::livewire('/', 'home')->name('home');
            
Pada app -> providers -> RouteServiceProvider.php ubah :

            public const HOME = '/';
            
# Edit navbar
Buka folder resources -> views -> layouts -> app.blade.php lalu cut kode navbar dan paste ke folder resources -> views -> livewire -> navbar.blade.php

Ubah sedikit kode pada navbar.blade.php :

            <nav class="navbar navbar-expand-md navbar-light bg-white">
                    <div class="container">
                        <a class="navbar-brand" href="{{ url('/') }}">
                            <strong>E</strong>-Shop
                        </a>

Pada folder resources -> views -> layouts -> app.blade.php ketikan pada tempat navbar sebelumnya :

            <livewire:navbar/>
Pada folder resources -> views -> livewire -> navbar.blade.php tambahkan :

            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <!-- Left Side Of Navbar -->
                <ul class="navbar-nav mr-auto">
                    <li class="nav-item">
                        <a class="nav-link" href="{{ route('home') }}">Home</a>
                    </li>
                </ul>

# Edit font
Buka google font -> pilih yang sesuai -> buka embed -> copy <link> -> paste pada folder (resources -> views -> layouts -> app.blade.php) -> replace pada <link href" ">

## Buat CSS baru
Pada folder public -> css -> create file (custom.css).

Isikan :

            body {
                 font-family: 'PT Sans', sans-serif; --> Didapat dari google font pada CSS rules
            }
            
## linking new CSS
Pada folder resources -> views -> layouts -> app.blade.php bagian style tambahkan :

            <link href="{{ asset('css/custom.css') }}" rel="stylesheet">
            
# Edit Home Page
Pada folder app -> http -> livewire -> Home.php tambahkan :

        use App\Liga;
        use App\Product;
        
        return view('livewire.home', [
            'products' => Product::take(4)->get(),
            'ligas' => Liga::all()
        ]);
        
Delete file home.blade.php dan welcome.blade.php yang ada pada folder resources -> views -> home.blade.php. hapus saja karena tidak digunakan.

# Build Home Page
Pada folder resources -> views -> livewire -> home.blade.php tambahan :

            <div class="container">

                {{-- BANNER --}}
                <div class="banner">
                    <img src="{{ url('assets/slider/slider1.png') }}" alt="">
                </div>

                {{-- PILIH-LIGA  --}}
                <section class="pilih-liga mt-4">
                    <h3><strong>Pilih Liga</strong></h3>
                    <div class="row mt-4">
                        @foreach( $ligas as $liga )
                            <div class="col">
                                <div class="card shadow">
                                    <div class="card-body text-center">
                                    <img src="{{ url('assets/liga') }}/{{ $liga->gambar }}" class="img-fluid">
                                    </div>
                                </div>
                            </div>
                        @endforeach
                    </div>
                </section>

                {{-- BEST-PRODUCT  --}}
                <section class="product mt-5 mb-4">
                    <h3><strong>Best Product</strong></h3>
                    <div class="row mt-4">
                        @foreach( $products as $product )
                            <div class="col-md-3">
                                <div class="card">
                                    <div class="card-body text-center">
                                    <img src="{{ url('assets/jersey') }}/{{ $product->gambar }}" class="img-fluid">
                                    <div class="row mt-2">
                                        <div class="col-md-12">
                                            <h5><strong> {{ $product->nama }} </strong></h5>
                                            <h5>Rp. {{ number_format( $product->harga ) }} </h5>
                                        </div>
                                    </div>
                                    <div class="row mt-2">
                                        <div class="col-md-12">
                                            <a href="#" class="btn btn-dark btn-block">Detail</a>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                        @endforeach
                    </div>
                </section>

Pada folder public -> css -> custom.css tambahkan :

            body {
                font-family: 'PT Sans', sans-serif;
                background-color: white;
            }

            .banner img {
                width: 100%;
                border-radius: 15px; /* membuat sisi sudut melengkung */
            }

            .pilih-liga img {
                max-height: 100px;
            }

            .pilih-liga .card {
                border-radius: 15px;
            }

            .product .card {
                border-radius: 15px;
            }
            
# Build Footer
Pada folder resources -> views -> layouts buat file baru didalam folder layout dengan nama footer.blade.php

Isikan : 

            <footer>
                <hr>
                <div class="container">
                    <div class="row mb-3">
                        <div class="col text-center">
                            Copyright @2020 E-shop.com
                        </div>
                    </div>
                </div>
            </footer>
            
Pada folder resources -> views -> layouts -> app.blade.php tambahkan dibagian body :

           <main class="py-4">
               @yield('content')
           </main>
           @include('/layouts/footer') 
           
# Edit Navbar
Pada folder resources -> views -> livewire -> navbar.blade.php tambahkan :

                      <li class="nav-item dropdown">
                        <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                          List Jersey
                        </a>
                        <div class="dropdown-menu" aria-labelledby="navbarDropdown">
                            @foreach ($ligas as $liga)
                                <a class="dropdown-item" href="#"> {{ $liga->nama }} </a>

                            @endforeach
                          <div class="dropdown-divider"></div>
                          <a class="dropdown-item" href="#">Semua Liga</a>
                        </div>
                      </li>
                      
Pada  folder app -> http -> livewire -> navbar.php tambahkan :

            return view('livewire.navbar', [
                        'ligas' => Liga::all()
                    ]);
                    
# Make List Jersey Page
            php artisan make:livewire ProductIndex
            
## Make routing
Pada folder routes -> web.php tambahkan :
            
            Route::livewire('/products', 'product-index')->name('products');
            
Pada folder resources -> views -> livewire -> navbar.blade.php ubah route semua liga :

            <div class="dropdown-divider"></div>
                   <a class="dropdown-item" href=" {{ route('products') }} ">Semua Liga</a>
                   
## Edit product index
Pada folder resources -> views -> livewire -> product-index.blade.php tambahkan :

           <div class="container">
                <div class="row mb-2">
                    <div class="col">
                        <nav aria-label="breadcrumb">
                            <ol class="breadcrumb">
                              <li class="breadcrumb-item"><a href=" {{ route('home') }} " class="text-dark">Home</a></li>
                              <li class="breadcrumb-item active" aria-current="page">List Jersey</li>
                            </ol>
                        </nav>
                    </div>
                </div>

                <h1>
                    List <strong>Jersey</strong>
                </h1>

                <section class="product mb-5">
                    <div class="row mt-4">
                        @foreach( $products as $product )
                            <div class="col-md-3 mb-3">
                                <div class="card">
                                    <div class="card-body text-center flex-fill">
                                    <img src="{{ url('assets/jersey') }}/{{ $product->gambar }}" class="img-fluid">
                                    <div class="row mt-2">
                                        <div class="col-md-12">
                                            <h5><strong> {{ $product->nama }} </strong></h5>
                                            <h5>Rp. {{ number_format( $product->harga ) }} </h5>
                                        </div>
                                    </div>
                                    <div class="row mt-2">
                                        <div class="col-md-12">
                                            <a href="#" class="btn btn-dark btn-block">Detail</a>
                                        </div>
                                    </div>
                                    </div>
                                </div>
                            </div>
                        @endforeach
                    </div>

                    <div class="row">
                        <div class="col">
                            {{ $products->links() }}
                        </div>
                    </div>
                </section>
            </div>

Pada folder public -> css -> custom.css tambahkan :

            .breadcrumb {
                background-color: transparent;
                padding: 0;
            }

            .breadcrumb .active {
                font-weight: bold;
                color: black;
            }
            
            .btn-dark {
                border-radius: 10px;
            }
            
Pada folder app -> http -> livewire -> ProductIndex.php tambahkan :

            use App\Product;
            use Livewire\Component;
            use Livewire\WithPagination;

            class ProductIndex extends Component
            {
                use WithPagination;

                public function render()
                {
                    $products = Product::paginate(8);
                    return view('livewire.product-index', [
                        'products' => $products
                    ]);
                }
            }
            
# Make search colloum
Pada folder app -> http -> livewire -> ProductIndex.php tambahkan :

               <div class="row">
                    <div class="col-md-9">
                        <h1>
                            List <strong>Jersey</strong>
                        </h1>
                    </div>
                    <div class="col-md-3">
                        <div class="input-group mb-3">
                            <input wire:model="search" type="text" class="form-control" placeholder="Search . . ." aria-label="Search" aria-describedby="basic-addon1">
                            <div class="input-group-prepend">
                                <span class="input-group-text" id="basic-addon1">
                                    <i class="fas fa-search"></i>
                                </span>
                              </div>
                        </div>
                    </div>
                </div>
            
Download font awesome di google -> ekstrak -> taruh pada folder (nama project laravel) -> public -> paste didalam folder public.

Pada folder resources -> views ->layouts -> app.blade.php tambahkan :

                <link href="{{ asset('fontawesome/css/all.min.css') }}" rel="stylesheet">

Pada folder app -> http -> livewire -> ProductIndex.php tambahkan :

                use WithPagination;

                public $search;

                protected $updateQueryString = ['search'];

                public function updatingSearch()
                {
                    $this->resetPage();
                }

                public function render()
                {
                    if($this->search) {
                        $products = Product::where('nama', 'like', '%'.$this->search.'%')->paginate(8);
                    }else {
                        $products = Product::paginate(8);
                    }

                    return view('livewire.product-index', [
                        'products' => $products
                    ]);
                }
                
# 
