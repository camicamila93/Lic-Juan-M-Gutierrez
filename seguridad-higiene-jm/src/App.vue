<template>
  <v-app>
    <!-- Banner principal -->
    <v-container fluid class="hero-banner d-flex align-center justify-center">
      <div class="text-center text-white">
        <h1 class="text-h2 font-weight-bold mb-2">Juan Mateo Gutiérrez</h1>
        <h2 class="text-h5 font-italic">Lic. en Seguridad e Higiene</h2>
      </div>
    </v-container>

    <!-- Sobre mí -->
    <v-container class="py-12">
      <h2 class="text-h4 font-weight-bold mb-4 text-primary">Sobre mí</h2>
      <p class="text-body-1">
        Soy Licenciado en Seguridad e Higiene con experiencia en prevención de riesgos laborales,
        asesoramiento técnico y capacitaciones para empresas e instituciones.
        Mi objetivo es garantizar ambientes de trabajo seguros, saludables y eficientes.
      </p>
    </v-container>

    <!-- Trabajos realizados -->
    <v-container class="py-12 grey-lighten-4">
      <h2 class="text-h4 font-weight-bold mb-6 text-primary">Trabajos realizados</h2>
      <v-row>
        <v-col cols="12" md="6" lg="4" v-for="n in 3" :key="n">
          <v-card>
            <v-img
              :src="'https://via.placeholder.com/400x250?text=Proyecto+' + n"
              height="250px"
            ></v-img>
            <v-card-text>
              <p>Descripción del proyecto {{ n }}. Aquí se puede incluir una foto o video del trabajo.</p>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>

    <!-- Servicios -->
    <v-container class="py-12">
      <h2 class="text-h4 font-weight-bold mb-6 text-primary">Servicios</h2>
      <v-row>
        <v-col cols="12" md="4" v-for="servicio in servicios" :key="servicio.titulo">
          <v-card class="pa-4 text-center">
            <v-icon size="48" color="primary">{{ servicio.icono }}</v-icon>
            <h3 class="text-h6 mt-3 font-weight-bold">{{ servicio.titulo }}</h3>
            <p class="mt-2">{{ servicio.descripcion }}</p>
          </v-card>
        </v-col>
      </v-row>
    </v-container>

    <!-- Contacto -->
    <v-footer color="primary" app class="pa-8 text-center text-white">
      <v-container>
        <h2 class="text-h5 mb-4 font-weight-bold">Contacto</h2>
        <p>📞 Teléfono: (3329) 555-123</p>
        <p>📍 San Pedro, Buenos Aires</p>
        <v-btn
          icon
          href="https://www.instagram.com/"
          target="_blank"
          class="mt-3"
          color="white"
        >
          <v-icon>mdi-instagram</v-icon>
        </v-btn>
      </v-container>
    </v-footer>
  </v-app>
</template>

<script setup>
import { ref } from "vue";

const servicios = ref([
  {
    titulo: "Asesoramiento Integral",
    descripcion:
      "Evaluaciones y planes de acción personalizados según las necesidades de tu empresa.",
    icono: "mdi-clipboard-check-outline",
  },
  {
    titulo: "Capacitaciones Laborales",
    descripcion:
      "Formación en seguridad, uso de elementos de protección y prevención de accidentes.",
    icono: "mdi-school-outline",
  },
  {
    titulo: "Auditorías Técnicas",
    descripcion:
      "Inspecciones y control del cumplimiento de normas de seguridad e higiene.",
    icono: "mdi-magnify",
  },
]);
</script>

<style scoped>
.hero-banner {
  background: url('https://images.unsplash.com/photo-1564069114553-7215e1ff1890?auto=format&fit=crop&w=1600&q=80')
    center center / cover no-repeat;
  height: 80vh;
}
.text-primary {
  color: #0d47a1 !important;
}
</style>