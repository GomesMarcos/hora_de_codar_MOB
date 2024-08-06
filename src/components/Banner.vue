<template>
  <div id="main-banner">
    <h2>Make Your Burger</h2>
  </div>
</template>

<script>
export default {
  name: "BannerVue",
};
</script>

<style scoped>
#main-banner {
  background-image: url("/public/img/burger.jpg");
  background-position: 0 -250px;
  background-size: cover;
  background-repeat: no-repeat;
  width: 100%;
  aspect-ratio: 19/8;
  display: flex;
  justify-content: flex-start;
  align-items: center;
}

#main-banner h2 {
  color: white;
  text-align: center;
  font-size: 64px;
  background-color: #222;
  padding: 20px;
}
</style>
