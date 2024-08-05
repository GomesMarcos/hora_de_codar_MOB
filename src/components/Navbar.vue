<script>
export default {
  name: "NavbarComponent",
};
</script>
<style scoped></style>
<template>
  <nav>
    <router-link to="/">
      <img src="/img/logo.png" alt="logo" id="logo" />
    </router-link>
    <router-link to="/">Home</router-link> |
    <router-link to="/pedidos">Pedidos</router-link>
  </nav>
</template>
