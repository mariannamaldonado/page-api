<template>
<!-- inicio -->

<div id="carouselExampleCaptions" class="carousel slide" data-bs-ride="carousel">
  <div class="carousel-indicators">
    <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
    <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="1" aria-label="Slide 2"></button>
    <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="2" aria-label="Slide 3"></button>
  </div>
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img src="../assets/photo1.jpg" class="d-block w-100" alt="">
      <div class="carousel-caption d-none d-md-block">
         <h1>Lo mejor de <br>Madrid</h1>
        <p>¡No te vayas a casa! Cada día en Madrid hay una propuesta perfecta para ti..</p>
      </div>
    </div>
    <div class="carousel-item">
      <img src="../assets/photo1.jpg" class="d-block w-100" alt="">
      <div class="carousel-caption d-none d-md-block">
        <h1>Lo mejor de <br>Madrid</h1>
        <p>¡No te vayas a casa! Cada día en Madrid hay una propuesta perfecta para ti..</p>
      </div>
    </div>
    <div class="carousel-item">
      <img src="../assets/photo1.jpg" class="d-block w-100" alt="">
      <div class="carousel-caption d-none d-md-block">
        <h1>Lo mejor de <br>Madrid</h1>
        <p>¡No te vayas a casa! Cada día en Madrid hay una propuesta perfecta para ti..</p>
      </div>
    </div>
  </div>
  <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleCaptions"  data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleCaptions"  data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </button>
</div>
<!-- fin  -->
      
        <div class="about" id="about">
            <div class="row">
                <div class="col-lg-6 col-12">
                    <div class="img"><img src="../assets/principal.jpg"></div>
                </div>
                <div class="col-lg-6 col-12 text-right">
                    <div class="about-child">
                        <h2 class="text-uppercase"></h2>
                        <p>¡No te vayas a casa! Cada día en Madrid hay una propuesta perfecta para ti..</p>
                        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptLorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et </p>
                        <a href="#"><i class="fas fa-long-arrow-alt-left fa-2x"></i><span>Leer más</span></a>
                    </div>
                </div>
            </div>
        </div>
        
        <div class="services" id="service">
            <div class="container"><h2 class="text"><span>Planes </span> en la ciudad</h2></div>
            <div class="services-child">
                <div class="container">
                    <div class="row">
                        <div class="col-lg-4 col-md-6 col-12">
                            <div>
                                <img src="../assets/museo1.jpg">
                                <router-link class="nav-link" to="/test"><h4>Museos</h4></router-link> 
                                <p><b>Museos imprescindibles en Madrid</b> <br/><br/> Madrid puede presumir de tener algunos de los museos más importantes del mundo</p>
                            </div>
                        </div>
                        <div class="col-lg-4 col-md-6 col-12">
                            <div>
                                <img src="../assets/almendros.jpg">
                                <router-link class="nav-link" to="/test"><h4>Parques</h4></router-link> 
                                <p><b>La primavera ha llegado prematura.</b> <br/> En el número 527 de la madrileña calle de Alcalá uno puede escaparse por unas horas de la gran ciudad y disfrutar de este espectáculo natural que anticipa la primavera. <br/> Hay que estar atentos con las fechas para no perderse este efímero acontecimiento.</p>
                            </div>
                        </div>
                        <div class="col-lg-4 col-md-6 col-12">
                            <div>
                                <img src="../assets/planes.jpg">
                                <router-link class="nav-link" to="/test"><h4>Eventos</h4></router-link> 
                                <p><b>No te pierdas ninguno de los planes para hacer en Madrid</b></p>
                            </div>
                        </div>
                    </div>
                    <a href="/Test"><i class="fas fa-long-arrow-alt-left fa-2x"></i><span>Leer más</span></a>
                </div>
            </div>
        </div>
        
        <div class="project">
            <div class="container"><h2 class="text-capitalize"><span>Eventos</span> Recientes</h2></div>
            <div class="project-child">
                <div class="container">
                    <div class="row">
                        <div class="col-lg-4 col-md-6 col-12">
                            <div>
                                <a href="#"><img src="../assets/photo2.jpg">
                                     <div class="yellow-overlay d-flex align-items-center justify-content-center">
                                        <p>Cultura</p>
                                    </div>
                                </a>
                            </div>
                        </div>
                        <div class="col-lg-4 col-md-6 col-12">
                            <div>
                                <a href="#"><img src="../assets/photo2.jpg">
                                     <div class="yellow-overlay d-flex align-items-center justify-content-center">
                                        <p>Viajes</p>
                                    </div>
                                </a>
                            </div>
                        </div>
                        <div class="col-lg-4 col-md-6 col-12">
                            <div>
                                <a href="#"><img src="../assets/photo2.jpg">
                                    <div class="yellow-overlay d-flex align-items-center justify-content-center">
                                        <p>Barrios Trendy</p>
                                    </div>
                                </a>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <div class="contact" id="contact">
            <div class="container">
                <h2 class="text-capitalize"><span>Mapa</span></h2>
                <MapJl/>
                <Map/>
              </div>
            <div class="contact-child">
                <div class="container">
                    <div class="row">
                        <div class="col-lg-6 col-12">
                          
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
               
                <div class="attribution">
      Proyecto API 
      <a href="" target="_blank"
        >Fullstack</a
      >. hecho por: <a href="#">Marianna Maldonado</a>.
    </div>
           
         
</template>


<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import Map from '@/components/Map.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld,
    Map
  }
}
</script>

<style>


/* about */

.about {
    padding: 50px 0
}

.about .img {
    width: 85%;
}

.about .img img{
    width: 100%;
    height: auto;
}

.about .row > .col-lg-6:first-of-type {
    position: relative;
}

.about .about-child {
    width: 70%
}

.about .about-child > p:first-of-type {
    font-size: 20px;
    font-weight: bold;
}

.about  a {
    width: 170px;
    border: 2px solid #ffe25b;
    margin-top: 30px;
    text-align: left;
    color: black;
    float: right;
}

.about a i {
    padding: 5px 15px;
    color: black;
    background-color: #ffe25b
}

.about a span {
    margin-left: 20px;
    position: relative;
    bottom: 7px;
}



.services {
    margin-bottom: 50px
}

.services .container {
    overflow: hidden
}

.services .services-child {
    background-color: #ebebeb;
    padding: 60px 0;
}

.services img {
    width: 100%;
    height: 300px;
    margin-bottom: 20px
}

.services .col-lg-4 > div {
    width: 100%;
    height: 100%;
}

.services .link {
    border: 3px solid #ffe25b;
    width: 160px;
    float: right;
}

.services .row a {
    color: black;
}

.services .row a:hover {
    color: #ffe25b;
}

.services .container > a {
    width: 170px;
    border: 2px solid #ffe25b;
    margin-top: 30px;
    text-align: left;
    color: black;
    float: right;
}

.services .container > a i {
    padding: 5px 15px;
    color: black;
    background-color: #ffe25b
}

.services .container > a span {
    margin-left: 20px;
    position: relative;
    bottom: 7px;
}


.project .project-child {
    padding: 120px 0;
    background-color: #ffe25b;
}

.project img {
    width: 100%;
    height: 100%;
}

.project a {
    color: rgb(0, 0, 0);
}

.project .col-lg-4 {
    position: relative;
    height: 300px;
}

.project .col-lg-4:first-of-type, .project .col-lg-4:last-of-type {
    bottom: 60px
}

.project .col-lg-4:nth-of-type(2) {
    top: 60px;
}

.project .col-lg-4 > div {
    width: 100%;
    height: 100%;
    position: relative
}

.project .col-lg-4 > div .yellow-overlay {
    position: absolute;
    height: 100%;
    width: 100%;
    top: 0;
    left: 0;
    background-color: rgba(255, 226, 91, .91);
    opacity: 0;
}

.project .col-lg-4 > div .yellow-overlay p {
    text-align: center;
    font-size: 25px
}

.project .col-lg-4 > div:hover .yellow-overlay {
    opacity: 1
}

.project .yellow-overlay {
    -webkit-transition: all 1s ease;
    -moz-transition: all 1s ease;
    -o-transition: all 1s ease;
    transition: all 1s ease;
}


.contact {
    padding: 70px 0;
}





</style>
