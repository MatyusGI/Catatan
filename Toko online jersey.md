


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

# 
