<template>
  <v-container fluid class="banner d-flex flex-column align-center justify-center text-center">
    <div class="overlay"></div>
    <h1 class="title">Juan Mateo Gutiérrez</h1>
    <h2 class="subtitle">Lic. en Seguridad e Higiene</h2>
  </v-container>
</template>

<style scoped>
.banner {
  background-image: url('@/assets/banner.jpg');
  background-size: cover;
  background-position: center;
  height: 80vh;
  position: relative;
  color: white;
}
.overlay {
  background: rgba(0, 0, 0, 0.4);
  position: absolute;
  top: 0; left: 0; right: 0; bottom: 0;
}
.title {
  font-family: 'Poppins', sans-serif;
  font-size: 3rem;
  z-index: 1;
}
.subtitle {
  font-size: 1.5rem;
  z-index: 1;
}
</style>
