<template>
  <article>
    <section class="curved">
      <div><img class="logo" src="@/assets/imgs/LogoASE.png" /></div>
      <div class="text">
        <p>Elaboramos tus proyectos en tiempo requerido y con altos estándares de calidad.</p>
      </div>
      <div class="buttons">
        <RouterLink to="/projects">Nuestros Trabajos</RouterLink>
        <a @click="scrollToTarget('ContactUSId')">Contactanos</a>
      </div>
    </section>

    <section id="jobs" class="cont-swiper jobs">
      <div class="title-seccion">
        <h1>Portafolio de Servicios y Proyectos</h1>
      </div>
      <div class="line-black"></div>

      <div class="container-slide-services">
        <swiper
          :effect="'coverflow'"
          :grabCursor="true"
          :centeredSlides="true"
          :slidesPerView="'auto'"
          :coverflowEffect="{
            rotate: 25,
            stretch: -50,
            depth: 200,
            modifier: 1,
            slideShadows: false
          }"
          :pagination="true"
          :modules="modules"
          class="mySwiper"
        >
          <swiper-slide class="swiper-slide-services"
            ><img src="@/assets/imgs/Barandas_Icon.png"
          /></swiper-slide>
          <swiper-slide class="swiper-slide-services"
            ><img src="@/assets/imgs/Cubiertas_Icon.png"
          /></swiper-slide>
          <swiper-slide class="swiper-slide-services"
            ><img src="@/assets/imgs/Divisiones_Icon.png"
          /></swiper-slide>
          <swiper-slide class="swiper-slide-services"
            ><img src="@/assets/imgs/Persianas_Icon.png"
          /></swiper-slide>
          <swiper-slide class="swiper-slide-services"
            ><img src="@/assets/imgs/Pisos_Icon.png"
          /></swiper-slide>
          <swiper-slide class="swiper-slide-services"
            ><img src="@/assets/imgs/PortonesElectricos_Icon.png"
          /></swiper-slide>
          <swiper-slide class="swiper-slide-services"
            ><img src="@/assets/imgs/Techos_Icon.png"
          /></swiper-slide>
        </swiper>
      </div>
    </section>

    <section id="AboutUS" class="cont-aboutUS">
      <div>
        <h1>¿Quienes Somos?</h1>
      </div>
      <div class="container-aboutUS">
        <div class="cont-first-AboutUS">
          <h3 class="title-AboutUS">Nosotros</h3>
          <p>
            Somos una empresa con más de 10 años en el mercado dedicada a la manufactura e
            instalación de todo tipo de acabados para construcciones, contamos con personal
            capacitado para la producción e instalación optima a nivel nacional.
          </p>
        </div>
        <div class="cont-second-AboutUS">
          <h3 class="title-AboutUS">Misión</h3>
          <p>
            Nuestro principal enfoque es satisfacer la necesidad de nuestros clientes mediante
            estándares de calidad y puntualidad en los proyectos y obras relacionadas con los
            acabados para la construcción.
          </p>
        </div>
        <div class="cont-third-AboutUS">
          <h3 class="title-AboutUS">Visión</h3>
          <p>
            Para el 2027 ser una empresa líder en la región, en cuanto a importación, distribución y
            capacitación de sistemas de automatización de acceso vehicular y peatonal a nivel
            residencial, comercial e industrial.
          </p>
        </div>
      </div>
    </section>

    <section class="cont-jobs bg-gray">
      <div class="title-seccion">
        <h1>Proyectos</h1>
      </div>
      <div class="line-black"></div>
      <div class="container-jobs-slide">
        <div class="cont-slipe">
          <swiper
            :spaceBetween="20"
            :centeredSlides="true"
            :autoplay="{
              delay: 5000,
              disableOnInteraction: false
            }"
            :pagination="{
              clickable: true
            }"
            :navigation="true"
            :modules="modules"
            class="mySwiper"
          >
            <swiper-slide>
              <div class="swiper-slide swiper-slide-img mwh">
                <img src="@/assets/imgs/jobs/EspejoMadera.jpg" />
              </div>
            </swiper-slide>
            <swiper-slide>
              <div class="swiper-slide swiper-slide-img mwh">
                <img src="@/assets/imgs/jobs/Espejo.jpg" /></div
            ></swiper-slide>
            <swiper-slide>
              <div class="swiper-slide swiper-slide-img mwh">
                <img src="@/assets/imgs/jobs/Glamping.jpg" /></div
            ></swiper-slide>
            <swiper-slide>
              <div class="swiper-slide swiper-slide-img mwh">
                <img src="@/assets/imgs/jobs/Ventana_1.jpg" /></div
            ></swiper-slide>
            <swiper-slide>
              <div class="swiper-slide swiper-slide-img mwh">
                <img src="@/assets/imgs/jobs/Muebles.jpg" /></div
            ></swiper-slide>
          </swiper>
        </div>
        <div class="descripcion-jobs">
          <p>
            Somos <b>Acabados y Soluciones Exito</b>, brindamos asesoramiento en diseño y solucion a
            tus espacios. Elaboramos tus proyectos en <b>tiempo</b> requerido y con altos estándares
            de <b>calidad</b>.
          </p>
        </div>
      </div>
    </section>
  </article>
</template>

<script>
import { Swiper, SwiperSlide } from 'swiper/vue'
import 'swiper/css'
import 'swiper/css/pagination'
import 'swiper/css/navigation'
import 'swiper/css/effect-coverflow'
import '@/assets/main.css'
import { EffectCoverflow, Autoplay, Pagination, Navigation } from 'swiper/modules'

export default {
  components: {
    Swiper,
    SwiperSlide
  },
  setup() {
    return {
      modules: [EffectCoverflow, Autoplay, Pagination, Navigation]
    }
  },
  methods: {
    scrollToTarget(id) {
      const targetElement = this.$refs.targetElement
      const targetElementId = document.getElementById(id)
      window.scrollTo({
        top: targetElementId.offsetTop,
        behavior: 'smooth'
      })
    }
  }
}
</script>

<style>
.swiper-slide {
  background-position: center;
  background-size: cover;
  width: 200px;
}

.container-slide-services {
  width: 100%;
}

.swiper-slide img {
  display: block;
  width: 100%;
}

.mwh {
  width: 100%;
  height: 100%;
}
</style>
