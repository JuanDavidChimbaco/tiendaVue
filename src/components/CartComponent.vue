<template>
  <div :class="show? 'TheChariot' : 'nothing'">
    <div class="carrito">
      <button @click="$emit('carrito', !show)">X</button>
      <div>{{ user.nombre }}</div>
      <div>{{ user.apellido }}</div>
      <div>{{ user.edad }}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    show: Boolean,
    user: Object,
  },
};
</script>

<style scoped>
.TheChariot {
  display: block;
  position: fixed;
  top: 0;
  right: 0;
  height: 100vh;
  width: 35%;
  background: rgb(243, 236, 202);
  z-index: 100;
  transition: 0.4s;
}

.nothing {
  display: block;
  position: fixed;
  top: 0;
  right: 0;
  height: 100vh;
  width: 35%;
  background: rgb(243, 236, 202);
  z-index: 100;
  transition: 0.4s;
  transform: translateX(100%);
}
</style>