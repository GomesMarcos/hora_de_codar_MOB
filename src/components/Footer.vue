<script>
export default {
  name: "FooterComponent",
};
</script>

<style scoped>
footer {
  height: 200px;
  background-color: #222;
  color: #fcba03;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100vw;
}
</style>

<template>
  <footer>
    <p>Make Your Burger &copy; {{ new Date().getFullYear() }}</p>
  </footer>
</template>
