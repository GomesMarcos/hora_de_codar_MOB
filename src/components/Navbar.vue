<script>
export default {
  name: "NavbarComponent",
  props: ["logo", "alt"],
};
</script>

<style scoped>
#nav {
  background-color: #222;
  border-bottom: 4px solid #111;
  padding: 15px 50px;
  display: flex;
  justify-content: flex-end;
  align-items: center;
}

#nav a {
  color: #fcba03;
  text-decoration: none;
  margin: 12px;
  transition: 0.5s;
}

#nav a:hover {
  color: #fff;
}

#nav #logo-url {
  margin: auto;
  margin-left: 0;
}

#nav #logo-url img {
  width: 42px;
  aspect-ratio: 1;
}
</style>

<template>
  <nav id="nav">
    <router-link id="logo-url" to="/">
      <img :src="logo" :alt="alt" id="logo" />
    </router-link>
    <router-link to="/">Home</router-link>
    <router-link to="/pedidos">Pedidos</router-link>
  </nav>
</template>
