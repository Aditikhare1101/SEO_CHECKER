<script>
import {Router ,Route,Link} from "svelte-navigator";

</script>
<Router>
    <!-- ======= Services Section ======= -->
    <section id="services" class="services section-bg">
        <div class="container">
  
          <div class="section-title">
            <h2 style="padding-top: 70px;">Tools </h2>
            <p></p>
          </div>
  
          <div class="row">
            <div class="col-lg-4 col-md-6">
              <div class="icon-box">
                <div class="icon"><i class="bi bi-pc-display-horizontal" style="color: #ff689b;"></i></div>
                <h4 class="title"><Link to="Seochecker">SEO Checker</Link></h4>
                <p class="description">Test your website's search engine optimization. Get valuable tips for a better website optimization and higher rankings. </p>
              </div>
            </div>
            <div class="col-lg-4 col-md-6">
              <div class="icon-box">
                <div class="icon"><i class="bi bi-file-earmark-word" style="color: #e9bf06;"></i></div>
                <h4 class="title"><Link to="Keywordchecker">Keyword Checker</Link></h4>
                <p class="description">Check the on-page optimization for your website and make sure it is optimized correctly for important</p>
              </div>
            </div>
  
            <div class="col-lg-4 col-md-6" data-wow-delay="0.1s">
              <div class="icon-box">
                <div class="icon"><i class="bi bi-graph-up-arrow" style="color: #3fcdc7;"></i></div>
                <h4 class="title"><Link to="Ranking">TF*IDF</Link></h4>
                <p class="description">The TF*IDF analysis gives you valuable insights into the text optimization of good ranked websites. </p>
              </div>
            </div>
          </div>
        </div>
   </section>
  <!-- End Services Section -->


</Router>

<style>

    /*--------------------------------------------------------------
# Services
--------------------------------------------------------------*/
.services .icon-box {
  padding: 30px;
  position: relative;
  overflow: hidden;
  border-radius: 10px;
  margin: 0 10px 40px 10px;
  background: #fff;
  box-shadow: 0 10px 29px 0 rgba(68, 88, 144, 0.1);
  transition: all 0.3s ease-in-out;
  margin-bottom: 120px;
  margin-top: 100px;
}

.services .icon-box:hover {
  transform: translateY(-5px);
  
}

.services .icon {
  position: absolute;
  left: -20px;
  top: calc(50% - 30px);
}

.services .icon i {
  font-size: 64px;
  line-height: 1;
  transition: 0.5s;
}

.services .title {
  margin-left: 40px;
  font-weight: 700;
  margin-bottom: 15px;
  font-size: 18px;

}

.services .title a {
  color: #111;
}

.services .icon-box:hover .title a {
  color: #49b5e7;
}

.services .description {
  font-size: 14px;
  margin-left: 40px;
  line-height: 24px;
  margin-bottom: 0;
}
</style>