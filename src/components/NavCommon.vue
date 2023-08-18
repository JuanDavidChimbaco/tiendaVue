<template>
  <nav class="navXd">
    <img src="../assets/img/logo.jpg" class="img" />
    <router-link to="/" class="link">Home</router-link>
    <router-link to="/about" class="link">About</router-link>
    <router-link to="/contact" class="link">Contact</router-link>
    <button
      class="link cart"
      type="button"
      @click="$emit('carrito', !show)"
    >Carrito</button>
  </nav>
</template>

<script>
export default {
  name: "NavCommon",
  props: {
    show: Boolean,
  },
  data() {
    return {
    };
  },
  methods: {
  },
};
</script>

<style scoped>
.navXd {
  display: flex;
  justify-content: start;
  align-items: center;
  background-color: #ffffff;
  min-height: 50px;
}

.link {
  text-decoration: none;
  font-weight: bold;
  color: hsla(160, 100%, 37%, 1);
  transition: 0.4s;
  padding: 10px;
  margin-left: 10px;
}
.link:hover {
  background-color: hsla(160, 100%, 37%, 0.2);
  text-decoration: none;
  font-weight: bold;
  border-radius: 25%;
}

.img {
  width: 50px;
  height: 50px;
  margin-left: 20px;
}

.cart {
  margin-left: auto;
  margin-right: 20px;
  padding: 10px;
  border-radius: 25%;
  transition: 0.4s;
  cursor: pointer;
}
</style>