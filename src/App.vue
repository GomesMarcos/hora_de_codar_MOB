<script>
import NavbarVue from "./components/Navbar.vue";
import FooterVue from "./components/Footer.vue";

export default {
  components: {
    NavbarVue,
    FooterVue,
  },
};
</script>

<template>
  <NavbarVue />
  <router-view />
  <FooterVue />
</template>

<style></style>
