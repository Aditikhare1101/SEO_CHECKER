<script>
import {Router , Route ,Link} from "svelte-navigator";
import Footer from "./lib/pages/footer.svelte";
import Seochecker from "./lib/pages/seochecker.svelte";
import Keywordchecker from "./lib/pages/keywordchecker.svelte";
import Ranking from "./lib/pages/ranking.svelte";
import Tools from "./lib/pages/tools.svelte";
import Login from "./lib/pages/login.svelte";
</script>
<Router>


    <header id="header" class="fixed-top">
      <div class="container d-flex align-items-center justify-content-between">
    
         <h1 class="logo"><a href="/">SEO Checker</a></h1> 
    
    
         <nav id="navbar" class="navbar">
          <ul>
            <li><a class="nav-link scrollto " href="/">Home</a></li>
            <li class="dropdown"><a href="#"><span>Tools</span> <i class="bi bi-chevron-down"></i></a>
              <ul>
                <li><a href="Seochecker">SEO Checker</a></li>
                <li><a href="Keywordchecker">Keyword Checker</a></li>
                <li><a href="Ranking">TF*IDF</a></li>
              </ul>
            </li>
            <li><a class="nav-link scrollto " href="Login">Login</a></li>
          </ul>
          <i class="bi bi-list mobile-nav-toggle"></i>
        </nav><!-- .navbar -->
    
      </div>
    </header><!-- End Header -->
<Route>
      <!-- ======= Hero Section ======= -->
      <section id="hero" class="d-flex align-items-center">
    
        <div class="container">
          <div class="row">
            <div class="col-lg-6 pt-4 pt-lg-0 order-2 order-lg-1 d-flex flex-column justify-content-center">
              <h1>All-In-One SEO Software & Tools</h1>
              <h2>Our website checks your complete website, by crawling all linked pages. All found pages with errors, problems with the on-page optimization or problems regarding the page content like duplicate content are collected and displayed in each check section. Of course, you can also analyze all problems of a single page in our page browser.</h2>
              <div><a href="#about" class="btn-get-started scrollto">Get Started</a></div>
            </div>
            <div class="col-lg-6 order-1 order-lg-2 hero-img">
              <img src="./src/assets/images/hero-img.png" class="img-fluid" alt="">
            </div>
          </div>
        </div>
      </section><!-- End Hero -->

          <!-- ======= About Section ======= -->
          <section id="about" class="about">
            <div class="container-fluid">
      
              <div class="row">
                <div class="col-xl-5 col-lg-6 video-box d-flex justify-content-left align-items-stretch" data-aos="fade-right">
                  <img  src="./src/assets/images/logo.png" class="img-fluid" alt="">
                </div>
      
                <div class="col-xl-7 col-lg-6 icon-boxes d-flex flex-column align-items-stretch justify-content-center py-5 px-lg-5" data-aos="fade-left">
                  <h3>SEO Checker comes with all SEO analyses and tools you need</h3>
                  <p>  Build better websites quickly, easily and of course sustainably</p>
      
                  <div class="icon-box" data-aos="zoom-in" data-aos-delay="100">
                    <div class="icon"><i class="bi bi-gear"></i></div>
                    <h4 class="title"><a href="/">On-Site Audit</a></h4>
                    <p class="description">Our crawler checks your entire website and follows all internal
                      and external links</p>
                  </div>
      
                  <div class="icon-box" data-aos="zoom-in" data-aos-delay="200">
                    <div class="icon"><i class="bi bi-bar-chart-line-fill"></i></div>
                    <h4 class="title"><a href="/">Rank Tracking</a></h4>
                    <p class="description">Track daily keyword rankings on different search engines and
                      country or city levels</p>
                  </div>
      
                  <div class="icon-box" data-aos="zoom-in" data-aos-delay="300">
                    <div class="icon"><i class="bi bi-link"></i></div>
                    <h4 class="title"><a href="/">Backlink Checker</a></h4>
                    <p class="description">Monitor SEO Backlinks, spy on your competitors and find ideas
                      for link building</p>
                  </div>
      
                </div>
              </div>
      
            </div>
            <Tools/>

      </section><!-- End About Section -->
  </Route>      
  

<Route path="Seochecker/*Seochecker" component ={Seochecker}/>
<Route path="Keywordchecker/*Keywordchecker" component ={Keywordchecker}/>
<Route path="Ranking/*Ranking" component ={Ranking}/>
<Route path="Login/*Login" component ={Login}/>
  <Footer />
</Router>



       





