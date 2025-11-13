<template>
  <v-app>
    <!-- Banner principal -->
    <v-container fluid class="pa-0">
      <v-img
        src="@/assets/banner.jpg"
        height="400"
        class="d-flex align-center justify-center"
        gradient="to bottom, rgba(0,0,0,0.3), rgba(0,0,0,0.6)"
      >
        <div class="text-center white--text">
          <h1 class="text-h3 font-weight-bold mb-2">Juan Mateo Gutiérrez</h1>
          <h2 class="text-subtitle-1">Lic. en Seguridad e Higiene</h2>
        </div>
      </v-img>
    </v-container>

    <!-- Sobre mí -->
    <v-container class="text-center my-12">
      <h2 class="text-h4 mb-4">Sobre mí</h2>
      <p class="mx-auto" style="max-width: 700px;">
        Soy profesional en Seguridad e Higiene, dedicado a garantizar entornos de trabajo seguros, eficientes y en cumplimiento con las normativas vigentes. 
        Este espacio está destinado a contar mi recorrido profesional y compartir experiencias.
      </p>
    </v-container>

    <!-- Trabajos realizados -->
    <v-container class="text-center my-12">
      <h2 class="text-h4 mb-4">Trabajos realizados</h2>
      <v-row>
        <v-col
          v-for="(trabajo, i) in trabajos"
          :key="i"
          cols="12"
          md="4"
        >
          <v-card>
            <v-img :src="trabajo.img" height="200"></v-img>
            <v-card-title>{{ trabajo.titulo }}</v-card-title>
            <v-card-text>{{ trabajo.descripcion }}</v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>

    <!-- Servicios -->
    <v-container class="text-center my-12">
      <h2 class="text-h4 mb-4">Servicios</h2>
      <v-row>
        <v-col
          v-for="(servicio, i) in servicios"
          :key="i"
          cols="12"
          md="4"
        >
          <v-card>
            <v-img :src="servicio.img" height="200"></v-img>
            <v-card-title>{{ servicio.titulo }}</v-card-title>
            <v-card-text>{{ servicio.descripcion }}</v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>

    <!-- Contacto -->
    <v-footer color="grey-darken-3" class="white--text pa-8">
      <v-container>
        <v-row align="center" justify="center" class="text-center">
          <v-col cols="12" md="4">
            <p class="mb-2">📞 Teléfono: (03329) 123456</p>
            <a
              href="https://instagram.com/usuario.ejemplo"
              target="_blank"
              class="white--text text-decoration-none"
            >
              📷 Instagram: @usuario.ejemplo
            </a>
            <p class="mt-2">📍 San Pedro, Buenos Aires</p>
          </v-col>
        </v-row>
        <v-row justify="center" class="mt-4">
          <p class="text-caption">© {{ new Date().getFullYear() }} Juan Mateo Gutiérrez - Todos los derechos reservados</p>
        </v-row>
      </v-container>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      trabajos: [
        { titulo: "Obra industrial", descripcion: "Supervisión de condiciones de seguridad en planta.", img: "https://via.placeholder.com/400x200" },
        { titulo: "Capacitaciones", descripcion: "Charlas de seguridad laboral para empleados.", img: "https://via.placeholder.com/400x200" },
        { titulo: "Consultorías", descripcion: "Asesoramiento en prevención de riesgos.", img: "https://via.placeholder.com/400x200" },
      ],
      servicios: [
        { titulo: "Asesoramiento técnico", descripcion: "Diagnóstico y evaluación de condiciones de seguridad.", img: "https://via.placeholder.com/400x200" },
        { titulo: "Auditorías", descripcion: "Control de cumplimiento normativo.", img: "https://via.placeholder.com/400x200" },
        { titulo: "Capacitaciones", descripcion: "Charlas y entrenamientos personalizados.", img: "https://via.placeholder.com/400x200" },
      ],
    }
  }
}
</script>

<style>
body {
  font-family: 'Roboto', sans-serif;
  background-color: #f7f7f7;
  color: #333;
}
h2 {
  color: #2e3b4e;
}
</style>