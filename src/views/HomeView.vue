<template>
  <div class="box">
    <header class="header">
      <div class="container">
        <div class="row align-items-center">
          <div class="col-4 text-center marquee-container">
            <div class="marquee-content">
              <div>
                <h1 class="title">Exotic Shoes</h1>
              </div>
              <div>
                <h1 class="title">Exotic Shoes</h1>
              </div>
            </div>
          </div>
          <div class="col-4 text-right">
            <p class="phone">
              <i class="fas fa-regular fa-phone"></i> 316 7599628
            </p>
          </div>
        </div>
      </div>
    </header>

    <NavCommon :show="show" v-on:carrito="this.show = $event"></NavCommon>
    {{show}}
    <div id="carouselExample" class="carousel slide">
      <div class="carousel-inner">
        <div class="carousel-item active">
          <div class="flexD">
            <img src="../assets/img/logo.jpg" class="d-block w-100 img" alt="..." />
          </div>
        </div>
        <div class="carousel-item">
          <div class="flexD">
            <img src="../assets/img/logo.jpg" class="d-block w-100 img" alt="..." />
          </div>
        </div>
        <div class="carousel-item">
          <div class="flexD">
            <img src="../assets/img/5594188.jpg" class="d-block w-100 img" alt="..." />
          </div>
        </div>
      </div>
      <button
        class="carousel-control-prev"
        type="button"
        data-bs-target="#carouselExample"
        data-bs-slide="prev"
      >
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Previous</span>
      </button>
      <button
        class="carousel-control-next"
        type="button"
        data-bs-target="#carouselExample"
        data-bs-slide="next"
      >
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Next</span>
      </button>
    </div>

    <CartComponent :show="show" :user="user" v-on:carrito="this.show = $event"></CartComponent>
    <div class="form-control">
      <label for class="form-label">nombre</label>
      <input type="text" name="name" id="name" v-model="user.nombre" class="form-control" />
      <label for class="form-label">apellido</label>
      <input type="text" name="name" id="apellido" v-model="user.apellido" class="form-control" />
      <label for class="form-label">edad</label>
      <input type="number" name="name" id="edad" v-model="user.edad" class="form-control" />
      <button @click="show = true" class="btn btn-dark">
        <i class="fa-solid fa-share"></i>Enviar
      </button>
    </div>

    <footer class="bg-dark text-light py-4">
      <div class="container">
        <div class="row">
          <div class="col-md-4">
            <h4>Redes sociales</h4>
            <ul class="list-unstyled">
              <li>
                <a href="https://l.wl.co/l?u=https%3A%2F%2Fwww.facebook.com%2Fshoesadrian%2F">
                  <i class="fab fa-facebook"></i> Facebook
                </a>
              </li>
              <li>
                <a href="#">
                  <i class="fab fa-twitter"></i> Twitter
                </a>
              </li>
              <li>
                <a href="#">
                  <i class="fab fa-instagram"></i> Instagram
                </a>
              </li>
            </ul>
          </div>
          <div class="col-md-4">
            <h4>Contacto</h4>
            <p>Teléfono: +57 316 7599628</p>
            <p>Email: info@example.com</p>
            <p>Direccion: municipio de Palermo Huila</p>
          </div>
          <div class="col-md-4">
            <h4>Sobre nosotros</h4>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc sodales pretium felis, at varius nunc feugiat in.</p>
          </div>
        </div>
        <div class="row mt-4">
          <div class="col-12">
            <p class="text-center">
              Desarrollado por
              <strong>Team - ADSO 2449133</strong>
            </p>
          </div>
        </div>
        <div class="row mt-2">
          <div class="col-12">
            <p class="text-center">&copy; 2023 Exotic Shoes. Todos los derechos reservados.</p>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
import NavCommon from "../components/NavCommon.vue";
import CartComponent from "../components/CartComponent.vue";

export default {
  components: {
    NavCommon,
    CartComponent,
  },
  data() {
    return {
      show: false,
      user: {
        nombre: "",
        apellido: "",
        edad: "",
      },
    };
  },
  methods: {},
};
</script>

<style scoped>
.box {
  display: grid;
}

#carouselExample {
  width: 80%;
  align-self: center;
  justify-self: center;
  background: #ffd7d7;
  border-radius: 10px;
  margin: 25px 0px;
  padding: 10px;
  -webkit-box-shadow: 0px 15px 15px -6px rgba(0, 0, 0, 0.75);
  -moz-box-shadow: 0px 15px 15px -6px rgba(0, 0, 0, 0.75);
  box-shadow: 0px 15px 15px -6px rgba(0, 0, 0, 0.75);
}

.flexD {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 100%;
}

.img {
  height: 500px;
  object-fit: contain;
  object-position: center;
}

.carousel-control-prev:hover {
  background: linear-gradient(-90deg, #ffffff00, #b05e5e);
  border-radius: 10px 0px 0px 10px;
}

.carousel-control-next:hover {
  background: linear-gradient(90deg, #ffffff00, #b05e5e);
  border-radius: 0px 10px 10px 0px;
}

.header {
  height: 30px;
  background-color: #1a1a1a;
  position: static;
}

.title {
  font-size: 24px;
  font-weight: bold;
  color: #b1b1b1;
  margin: 0;
  font-family: "Franklin Gothic Medium", "Arial Narrow", Arial, sans-serif;
}

.phone {
  font-size: 10px;
  color: #b1b1b1;
  margin: 0;
}

.marquee-container {
  overflow: hidden; /* Ocultar el contenido que se desborda */
  position: relative; /* Establecer posición relativa para posicionar el contenido dentro */
  height: 2rem; /* Ajustar la altura según sea necesario */
}

.marquee-container .marquee-content {
  position: absolute; /* Establecer posición absoluta para desplazarse fuera del contenedor */
  animation: marquee 5s linear infinite; /* Agregar animación */
  overflow: hidden;
  width: 200%;
}

.marquee-container .marquee-content div {
  float: left;
  width: 50%;
}

@keyframes marquee {
  0% {
    left: 0;
  }
  100% {
    left: -100%;
  }
}
</style>
