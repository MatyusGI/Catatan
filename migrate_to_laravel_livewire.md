# Copy head
yang di copy :
    
    <meta content="width=device-width, initial-scale=1.0" name="viewport">
    <meta content="riset, kedokteran, statistik, bioinformmatika" name="keywords">
    <meta content="Kami melayani hal-hal yang berkaitan dengan manajemen riset" name="description">

    <!-- Favicons -->
    <link rel="icon" type="image/png" href="img/favicon-32x32.png" sizes="32x32" />
    <link rel="apple-touch-icon-precomposed" sizes="120x120" href="img/apple-touch-icon-120x120.png" />

    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css?family=Open+Sans:300,400,400i,600,700|Raleway:300,400,400i,500,500i,700,800,900" rel="stylesheet">

    <!-- Bootstrap CSS File -->
    <link href="lib/bootstrap/css/bootstrap.min.css" rel="stylesheet">

    <!-- Libraries CSS Files -->
    <link href="lib/nivo-slider/css/nivo-slider.css" rel="stylesheet">
    <link href="lib/owlcarousel/owl.carousel.css" rel="stylesheet">
    <link href="lib/owlcarousel/owl.transitions.css" rel="stylesheet">
    <link href="lib/font-awesome/css/font-awesome.min.css" rel="stylesheet">
    <link href="lib/animate/animate.min.css" rel="stylesheet">
    <link href="lib/venobox/venobox.css" rel="stylesheet">

    <!-- Nivo Slider Theme -->
    <link href="css/nivo-slider-theme.css" rel="stylesheet">

    <!-- Main Stylesheet File -->
    <link href="css/style.css" rel="stylesheet">

    <!-- Responsive Stylesheet File -->
    <link href="css/responsive.css" rel="stylesheet">

    <link href="css/quiz_style.css" rel="stylesheet">

    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    <script src="https://unpkg.com/vue-router/dist/vue-router.js"></script>

karena menggunakan livewire sehingga untuk mengakses file pada folder memerlukan {{ asset(' ') }}, sehingga saat dipindah menjadi (sudah termasuk kode dari livewire) :

    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1">

        <!-- CSRF Token -->
        <meta name="csrf-token" content="{{ csrf_token() }}">

        <title>{{ config('app.name', 'akarilmiah') }}</title>
        <meta content="width=device-width, initial-scale=1.0" name="viewport">
        <meta content="riset, kedokteran, statistik, bioinformmatika" name="keywords">
        <meta content="Kami melayani hal-hal yang berkaitan dengan manajemen riset" name="description">

        <!-- Scripts -->
        <script src="{{ asset('js/app.js') }}" defer></script>

        <!-- Fonts -->
        <link rel="dns-prefetch" href="//fonts.gstatic.com">
        <link href="https://fonts.googleapis.com/css?family=Nunito" rel="stylesheet">

        <!-- Styles -->
        {{-- <link href="{{ asset('css/app.css') }}" rel="stylesheet"> --}} --> di komen karena tidak digunakan

        <!-- Favicons -->
        <link rel="apple-touch-icon-precomposed" sizes="120x120" href="{{ asset('img/apple-touch-icon-120x120.png') }}" >
        <link rel="shortcut icon" type="image/png" href="{{ asset('img/favicon-32x32.png') }}" sizes="32x32" >

        <!-- Google Fonts -->
        <link href="https://fonts.googleapis.com/css?family=Open+Sans:300,400,400i,600,700|Raleway:300,400,400i,500,500i,700,800,900" rel="stylesheet">

        <!-- Bootstrap CSS File -->
        <link href="{{ asset('css/lib/bootstrap/css/bootstrap.min.css') }}" rel="stylesheet">

        <!-- Libraries CSS Files -->
        <link href="{{ asset('css/lib/nivo-slider/css/nivo-slider.css') }}" rel="stylesheet">
        <link href="{{ asset('css/lib/owlcarousel/owl.carousel.css') }}" rel="stylesheet">
        <link href="{{ asset('css/lib/owlcarousel/owl.transitions.css') }}" rel="stylesheet">
        <link href="{{ asset('css/lib/font-awesome/css/font-awesome.min.css') }}" rel="stylesheet">
        <link href="{{ asset('css/lib/animate/animate.min.css') }}" rel="stylesheet">
        <link href="{{ asset('css/lib/venobox/venobox.css') }}" rel="stylesheet">

        <!-- Nivo Slider Theme -->
        <link href="{{ asset('css/nivo-slider-theme.css') }}" rel="stylesheet">

        <!-- Main Stylesheet File -->
        <link href="{{ asset('css/style.css') }}" rel="stylesheet">

        <!-- Responsive Stylesheet File -->
        <link href="{{ asset('css/responsive.css') }}" rel="stylesheet">

        <link href="{{ asset('css/quiz_style.css') }}" rel="stylesheet">

        <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
        <script src="https://unpkg.com/vue-router/dist/vue-router.js"></script>

        <livewire:styles/>
        <livewire:scripts/>

    </head>
    
note : sudah memindahkan atau copy folder atau file yang dibutuhkan kedalam folder public
    
# Edit Body
pada body ditambahkan :

    <body data-spy="scroll" data-target="#navbar-example">
    
    </body>

membuat navbar, slider, dan quiz dengan file terpisah :

    <livewire:navbar/>
    <livewire:slider/>
    <livewire:statq/>
    
menambah javascript pada bagian body (sebelumnya sudah mengcopy folder lib, contactform, dan js kedalam folder public) :

    <!-- JavaScript Libraries -->
    <script src="lib/jquery/jquery.min.js"></script>
    <script src="lib/bootstrap/js/bootstrap.min.js"></script>
    <script src="lib/owlcarousel/owl.carousel.min.js"></script>
    <script src="lib/venobox/venobox.min.js"></script>
    <script src="lib/knob/jquery.knob.js"></script>
    <script src="lib/wow/wow.min.js"></script>
    <script src="lib/parallax/parallax.js"></script>
    <script src="lib/easing/easing.min.js"></script>
    <script src="lib/nivo-slider/js/jquery.nivo.slider.js" type="text/javascript"></script>
    <script src="lib/appear/jquery.appear.js"></script>
    <script src="lib/isotope/isotope.pkgd.min.js"></script>

    <!-- Contact Form JavaScript File -->
    <script src="contactform/contactform.js"></script>
    <script src="js/main.js"></script>
    
karena menggunakan livewire sehingga untuk mengakses file pada folder memerlukan {{ asset(' ') }}, sehingga saat dipindah menjadi :

    <!-- JavaScript Libraries -->
    <script src="{{ asset('lib/jquery/jquery.min.js') }}"></script>
    <script src="{{ asset('lib/bootstrap/js/bootstrap.min.js') }}"></script>
    <script src="{{ asset('lib/owlcarousel/owl.carousel.min.js') }}"></script>
    <script src="{{ asset('lib/venobox/venobox.min.js') }}"></script>
    <script src="{{ asset('lib/knob/jquery.knob.js') }}"></script>
    <script src="{{ asset('lib/wow/wow.min.js') }}"></script>
    <script src="{{ asset('lib/parallax/parallax.js') }}"></script>
    <script src="{{ asset('lib/easing/easing.min.js') }}"></script>
    <script src="{{ asset('lib/nivo-slider/js/jquery.nivo.slider.js') }}" type="text/javascript"></script>
    <script src="{{ asset('lib/appear/jquery.appear.js') }}"></script>
    <script src="{{ asset('lib/isotope/isotope.pkgd.min.js') }}"></script>

    <!-- Contact Form JavaScript File -->
    <script src="{{ asset('contactform/contactform.js') }}"></script>
    <script src="{{ asset('js/main.js') }}"></script>
    
# Membuat navbar, slider, dan quiz
untuk membuat file navbar, slider dan quiz menggunakan perintah pada terminal :

    php artisan make:livewire navbar
    php artisan make:livewire slider
    php artisan make:livewire statq
    
setelah terbuat selanjutnya mengedit/copy isi masing masing tersebut

# Edit Navbar
copy ke navbar.blade.php :

    <header>
        <!-- header-area start -->
        <div id="sticker" class="header-area">
        <div class="container">
            <div class="row">
            <div class="col-md-12 col-sm-12">

                <!-- Navigation -->
                <nav class="navbar navbar-default">
                <!-- Brand and toggle get grouped for better mobile display -->
                <div class="navbar-header">
                    <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target=".bs-example-navbar-collapse-1" aria-expanded="false">
                        <span class="sr-only">Toggle navigation</span>
                        <span class="icon-bar"></span>
                        <span class="icon-bar"></span>
                        <span class="icon-bar"></span>
                    </button>
                    <!-- Brand -->
                    <a class="navbar-brand page-scroll sticky-logo" href="index.html">
                    <h1><span>akar</span>ilmiah</h1>
                    <!-- Uncomment below if you prefer to use an image logo -->
                    <!-- <img src="img/logo.png" alt="" title=""> -->
                                    </a>
                </div>
                <!-- Collect the nav links, forms, and other content for toggling -->
                <div class="collapse navbar-collapse main-menu bs-example-navbar-collapse-1" id="navbar-example">
                    <ul class="nav navbar-nav navbar-right">
                    <li class="active">
                        <a class="page-scroll" href="#home">Home</a>
                    </li>
                    <li>
                        <a class="page-scroll" href="#about">About</a>
                    </li>
                    <li>
                        <a class="page-scroll" href="#services">Services</a>
                    </li>
                    <li>
                        <a class="page-scroll" href="#team">Team</a>
                    </li>                   
                    <li>
                        <a class="page-scroll" href="#blog">Blog</a>
                    </li>
                    <li>
                        <a class="page-scroll" href="#contact">Contact</a>
                    </li>
                    </ul>
                </div>
                <!-- navbar-collapse -->
                </nav>
                <!-- END: Navigation -->
            </div>
            </div>
        </div>
        </div>
        <!-- header-area end -->
    </header>
    <!-- header end -->
    
# Edit slider
Copy ke slider.blade.php :

    <!-- Start Slider Area -->
      <div id="home" class="slider-area">
        <div class="bend niceties preview-2">
          <div id="ensign-nivoslider" class="slides">
            <img src="{{ asset('img/slider/slider1.jpg') }}" alt="" title="#slider-direction-1" />
            <img src="{{ asset('img/slider/slider2.jpg') }}" alt="" title="#slider-direction-2" />
            <img src="{{ asset('img/slider/slider3.jpg') }}" alt="" title="#slider-direction-3" />
          </div>
    
          <!-- direction 1 -->
          <div id="slider-direction-1" class="slider-direction slider-one">
            <div class="container">
              <div class="row">
                <div class="col-md-12 col-sm-12 col-xs-12">
                  <div class="slider-content">
                    <!-- layer 1 -->
                    <div class="layer-1-1 hidden-xs wow slideInDown" data-wow-duration="2s" data-wow-delay=".2s">
                      <h2 class="title1">Research Management </h2>
                    </div>
                    <!-- layer 2 -->
                    <div class="layer-1-2 wow slideInUp" data-wow-duration="2s" data-wow-delay=".1s">
                      <h1 class="title2">We Provide a Clear Pathway for Your Inquisitive Mind</h1>
                    </div>
                    <!-- layer 3 -->
                    <div class="layer-1-3 hidden-xs wow slideInUp" data-wow-duration="2s" data-wow-delay=".2s">
                      <a class="ready-btn right-btn page-scroll" href="#services">See Services</a>
                      <a class="ready-btn page-scroll" href="#about">Learn More</a>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
    
          <!-- direction 2 -->
          <div id="slider-direction-2" class="slider-direction slider-two">
            <div class="container">
              <div class="row">
                <div class="col-md-12 col-sm-12 col-xs-12">
                  <div class="slider-content text-center">
                    <!-- layer 1 -->
                    <div class="layer-1-1 hidden-xs wow slideInUp" data-wow-duration="2s" data-wow-delay=".2s">
                      <h2 class="title1">Oligo Synthesis</h2>
                    </div>
                    <!-- layer 2 -->
                    <div class="layer-1-2 wow slideInUp" data-wow-duration="2s" data-wow-delay=".1s">
                      <h1 class="title2">We Ease You Design Your Next Oligo</h1>
                    </div>
                    <!-- layer 3 -->
                    <div class="layer-1-3 hidden-xs wow slideInUp" data-wow-duration="2s" data-wow-delay=".2s">
                      <a class="ready-btn right-btn page-scroll" href="#services">See Services</a>
                      <a class="ready-btn page-scroll" href="#about">Learn More</a>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
    
          <!-- direction 3 -->
          <div id="slider-direction-3" class="slider-direction slider-two">
            <div class="container">
              <div class="row">
                <div class="col-md-12 col-sm-12 col-xs-12">
                  <div class="slider-content">
                    <!-- layer 1 -->
                    <div class="layer-1-1 hidden-xs wow slideInUp" data-wow-duration="2s" data-wow-delay=".2s">
                      <h2 class="title1">DNA Sequencing </h2>
                    </div>
                    <!-- layer 2 -->
                    <div class="layer-1-2 wow slideInUp" data-wow-duration="2s" data-wow-delay=".1s">
                      <h1 class="title2">Helping You with Our Best Sequencing Technology</h1>
                    </div>
                    <!-- layer 3 -->
                    <div class="layer-1-3 hidden-xs wow slideInUp" data-wow-duration="2s" data-wow-delay=".2s">
                      <a class="ready-btn right-btn page-scroll" href="#services">See Services</a>
                      <a class="ready-btn page-scroll" href="#about">Learn More</a>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <!-- End Slider Area -->
      
# Edit Quiz
Copy ke statq.blade.php :

        <!-- Start StatQ area-->
    <div id="app" class="app-area area-padding" v-cloak>
        <div class="container">
        <div class="row">
            <div class="col-md-12 col-sm-12 col-xs-12">
            <h1>{{ quiz.title }}</h1>

            <div v-for="(question, index) in quiz.questions">
                <div class="response-field" v-show="index === questionIndex">
                <h3>{{ question.text }}</h3>
                <ul>
                    <li v-for="response in question.responses">
                    <label>
                        <input type="radio"
                            v-bind:value="response.value"
                            v-bind:name="index"
                            v-model="userResponses[index]"> {{response.text}}
                    </label>
                    </li>
                </ul>
                </br>
                <button class="secondary button" style="margin-top:5px;" v-if="questionIndex > 0" v-on:click="prev">
                        prev
                        </button>
                <button class="success button" style="margin-left:5px; margin-top:5px;" v-on:click="next">
                        next
                        </button>
                </div>
            </div>
            <div v-show="questionIndex === quiz.questions.length">
                <h3>Uji statistik yang kamu butuhkan:</h3>
                <p>
                sekarang masih uji coba. <br>
                jadi belum ada yang betul.
                </p>
                
                <div class="coba">
                <h2 class="blurry-text">Foreverblur</h2>
                </div>
            
                <h3>Daftar untuk melihat penuh</h3>
                <div class="daftar">
                <input type="email" placeholder="masukan email">
                <button>Daftar sekarang</button>
                </div>
                <div id="pricing" class="pricing-area-view area-padding">
                <div class="container">
                    <div class="row">
                    <div class="col-md-12 col-sm-12 col-xs-12">
                        <div class="section-headline text-center">
                        <h2>Pricing Table</h2>
                        </div>
                    </div>
                    </div>
                    <div class="row">
                    <div class="col-md-4 col-sm-4 col-xs-12">
                        <div class="pri_table_list">
                        <h3>basic <br/> <span>Rp. 100.000,-</span></h3>
                        <ol>
                            <li class="check">Online system</li>
                            <li class="check cross">Full access</li>
                            <li class="check">Free apps</li>
                            <li class="check">Multiple slider</li>
                            <li class="check cross">Free domin</li>
                            <li class="check cross">Support unlimited</li>
                            <li class="check">Payment online</li>
                            <li class="check cross">Cash back</li>
                        </ol>
                        <button>sign up now</button>
                        </div>
                    </div>
                    <div class="col-md-4 col-sm-4 col-xs-12">
                        <div class="pri_table_list active">
                        <span class="saleon">Best Deal</span>
                        <h3>standard <br/> <span>Rp. 250.000,-</span></h3>
                        <ol>
                            <li class="check">Online system</li>
                            <li class="check">Full access</li>
                            <li class="check">Free apps</li>
                            <li class="check">Multiple slider</li>
                            <li class="check cross">Free domin</li>
                            <li class="check">Support unlimited</li>
                            <li class="check">Payment online</li>
                            <li class="check cross">Cash back</li>
                        </ol>
                        <button>sign up now</button>
                        </div>
                    </div>
                    <div class="col-md-4 col-sm-4 col-xs-12">
                        <div class="pri_table_list">
                        <h3>premium <br/> <span>Rp. 500.000,-</span></h3>
                        <ol>
                            <li class="check">Online system</li>
                            <li class="check">Full access</li>
                            <li class="check">Free apps</li>
                            <li class="check">Multiple slider</li>
                            <li class="check">Free domin</li>
                            <li class="check">Support unlimited</li>
                            <li class="check">Payment online</li>
                            <li class="check">Cash back</li>
                        </ol>
                        <button>sign up now</button>
                        </div>
                    </div>
                    </div>
                </div>
                </div>
            </div>
            </div>
        </div>
        </div>
    </div>
    <!-- End of StatQ area -->
    
karena '<h1>{{ quiz.title }}</h1>', '<h3>{{ question.text }}</h3>', dan {{ response.text }} membutuhkan escape route untuk keluar dari regular expresion php sehingga dibutuhkan @{{quiz.title}}. code nya menjadi :

        <!-- Start StatQ area-->
    <div id="app" class="app-area area-padding" v-cloak>
        <div class="container">
        <div class="row">
            <div class="col-md-12 col-sm-12 col-xs-12">
            <h1>@{{ quiz.title }}</h1>

            <div v-for="(question, index) in quiz.questions">
                <div class="response-field" v-show="index === questionIndex">
                <h3>@{{ question.text }}</h3>
                <ul>
                    <li v-for="response in question.responses">
                    <label>
                        <input type="radio"
                            v-bind:value="response.value"
                            v-bind:name="index"
                            v-model="userResponses[index]"> @{{response.text}}
                    </label>
                    </li>
                </ul>
                </br>
                <button class="secondary button" style="margin-top:5px;" v-if="questionIndex > 0" v-on:click="prev">
                        prev
                        </button>
                <button class="success button" style="margin-left:5px; margin-top:5px;" v-on:click="next">
                        next
                        </button>
                </div>
            </div>
            <div v-show="questionIndex === quiz.questions.length">
                <h3>Uji statistik yang kamu butuhkan:</h3>
                <p>
                sekarang masih uji coba. <br>
                jadi belum ada yang betul.
                </p>
                
                <div class="coba">
                <h2 class="blurry-text">Foreverblur</h2>
                </div>
            
                <h3>Daftar untuk melihat penuh</h3>
                <div class="daftar">
                <input type="email" placeholder="masukan email">
                <button>Daftar sekarang</button>
                </div>
                <div id="pricing" class="pricing-area-view area-padding">
                <div class="container">
                    <div class="row">
                    <div class="col-md-12 col-sm-12 col-xs-12">
                        <div class="section-headline text-center">
                        <h2>Pricing Table</h2>
                        </div>
                    </div>
                    </div>
                    <div class="row">
                    <div class="col-md-4 col-sm-4 col-xs-12">
                        <div class="pri_table_list">
                        <h3>basic <br/> <span>Rp. 100.000,-</span></h3>
                        <ol>
                            <li class="check">Online system</li>
                            <li class="check cross">Full access</li>
                            <li class="check">Free apps</li>
                            <li class="check">Multiple slider</li>
                            <li class="check cross">Free domin</li>
                            <li class="check cross">Support unlimited</li>
                            <li class="check">Payment online</li>
                            <li class="check cross">Cash back</li>
                        </ol>
                        <button>sign up now</button>
                        </div>
                    </div>
                    <div class="col-md-4 col-sm-4 col-xs-12">
                        <div class="pri_table_list active">
                        <span class="saleon">Best Deal</span>
                        <h3>standard <br/> <span>Rp. 250.000,-</span></h3>
                        <ol>
                            <li class="check">Online system</li>
                            <li class="check">Full access</li>
                            <li class="check">Free apps</li>
                            <li class="check">Multiple slider</li>
                            <li class="check cross">Free domin</li>
                            <li class="check">Support unlimited</li>
                            <li class="check">Payment online</li>
                            <li class="check cross">Cash back</li>
                        </ol>
                        <button>sign up now</button>
                        </div>
                    </div>
                    <div class="col-md-4 col-sm-4 col-xs-12">
                        <div class="pri_table_list">
                        <h3>premium <br/> <span>Rp. 500.000,-</span></h3>
                        <ol>
                            <li class="check">Online system</li>
                            <li class="check">Full access</li>
                            <li class="check">Free apps</li>
                            <li class="check">Multiple slider</li>
                            <li class="check">Free domin</li>
                            <li class="check">Support unlimited</li>
                            <li class="check">Payment online</li>
                            <li class="check">Cash back</li>
                        </ol>
                        <button>sign up now</button>
                        </div>
                    </div>
                    </div>
                </div>
                </div>
            </div>
            </div>
        </div>
        </div>
    </div>
    <!-- End of StatQ area -->
    
#
