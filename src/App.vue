<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <nav :class="menuClass" ref="menu">
      <button class="nav-toggle">
        <img class="img-menu-button" src="@/assets/imgs/menu.png" width="30px" />
      </button>
      <ul class="nav-menu">
        <li>
          <RouterLink class="selected-item" to="/">Principal</RouterLink>
        </li>
        <li>
          <RouterLink to="/">¿Quienes Somos?</RouterLink>
        </li>
        <li><RouterLink to="/projects">Proyectos</RouterLink></li>
        <li><RouterLink to="/locateUS">Ubiquenos</RouterLink></li>
        <li><RouterLink to="/locateUS">Contactenos</RouterLink></li>
        <RouterLink to="/" class="img-logo-navbar"
          ><img src="@/assets/imgs/LogoASE.png"
        /></RouterLink>
      </ul>
    </nav>
  </header>

  <div class="whatsapp-btn">
    <a href="https://wa.me/+573102467622" target="_blank">
      <img src="@/assets/bg_wp.png" alt="WhatsApp Icon" />
    </a>
  </div>

  <div id="miPopup" class="popup">
    <p>Contactanos!</p>
  </div>

  <RouterView />
  <article ref="ContactUSId" id="ContactUSId" class="shadow principal-banner">
    <div class="background">
      <h1>Contactenos</h1>
    </div>
  </article>

  <article class="form-contact-seccion">
    <form>
      <input type="text" placeholder="Nombre Completo" />
      <input type="text" placeholder="Telefono" />
      <input type="email" placeholder="Correo Electronico" />
      <textarea placeholder="Descripción" rows="4" cols="50"></textarea>
      <input value="Solicitar Cotización" class="button-submit" type="submit" />
    </form>
  </article>
  <footer class="footer">
    <div><img class="cont-logo-footer" src="@/assets/imgs/LogoASE.png" /></div>

    <div class="cont-contact">
      <div class="contact-seccion contact-first-seccion">
        <p>
          <span class="text-gold">Contactanos</span><br />
          <a href="tel:(+57)3204234160">(+57) 320 423 4160</a><br />
          <a href="tel:(+57)3102467622">(+57) 310 246 7622</a><br />
          <a href="mailto:acabadosysolucionesexitoase@gmail.com">
            acabadosysolucionesexitoase@gmail.com </a
          ><br />
          <a href="https://www.facebook.com/profile.php?id=100084519013222" target="_blank">
            <img src="@/assets/imgs/Icon-Facebook.png" alt="linkFacebbok" class="size-icon" />
            <span class="text-icon">Facebook</span>
          </a>
          <a href="https://www.instagram.com/acabados_ysolucionesexito/" target="_blank">
            <img src="@/assets/imgs/Icon-Instagram.png" alt="linkInstagram" class="size-icon" />
            <span>Instagram</span>
          </a>
        </p>
      </div>

      <div class="contact-seccion contact-second-seccion">
        <p>
          <span class="text-gold">Tunja - Boyacá</span><br /><br />
          <b
            >Avenida Carrera 6 N° 59-47 <br />
            Barrio Villa Luz</b
          >
        </p>
      </div>
    </div>

    <div class="cont-copyrigth">
      <p>
        El uso de este sitio web implica la aceptación de los
        <a href="files/Terminos&Condiciones.pdf">Términos y Condiciones</a>
        y Políticas de privacidad de ACABADOS Y SOLUCIONES EXITO.
        <b>© 2022 Todos los derechos reservados.</b> Desarollado por
        <a href="mailto: dasapibu@gmail.com">David Santiago Piña Bustos</a>
        .Prohibida su reproducción total o parcial, así como su traducción a cualquier idioma sin la
        autorización escrita de su titular.
      </p>
    </div>
  </footer>
</template>

<script>
export default {
  data() {
    return {
      menuClass: ''
    }
  },
  mounted() {
    this.$nextTick(() => {
      this.initMenu()
    })
  },
  methods: {
    initMenu() {
      window.addEventListener('scroll', this.handleScroll)
    },
    handleScroll() {
      const menuElement = this.$refs.menu
      const height = menuElement.offsetTop

      if (window.pageYOffset > height) {
        this.menuClass = 'menu-fixed'
      } else {
        this.menuClass = ''
      }
    }
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>
