<template>
  <v-container class="py-12">
    <h2 class="text-center mb-6">Servicios</h2>
    <v-row>
      <v-col cols="12" md="4" v-for="service in services" :key="service.title">
        <v-card class="pa-4 text-center">
          <v-icon size="48" color="primary">{{ service.icon }}</v-icon>
          <h3 class="mt-4">{{ service.title }}</h3>
          <p>{{ service.description }}</p>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
const services = [
  { title: 'Asesoramiento en Seguridad', icon: 'mdi-shield-check', description: 'Evaluación y gestión de riesgos laborales.' },
  { title: 'Capacitaciones', icon: 'mdi-school-outline', description: 'Formación a trabajadores y empleadores.' },
  { title: 'Auditorías', icon: 'mdi-file-search-outline', description: 'Análisis y mejora de condiciones de trabajo.' }
]
</script>
