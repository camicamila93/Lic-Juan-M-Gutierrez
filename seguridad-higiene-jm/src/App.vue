
<template>
  <v-app>
    <!-- Menú superior -->
    <v-app-bar
      color="green darken-4"
      density="comfortable"
      elevate-on-scroll
      dark
    >
      <v-toolbar-title class="font-weight-bold">Juan Mateo Gutiérrez</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn text @click="scrollTo('about')">Sobre mí</v-btn>
      <v-btn text @click="scrollTo('projects')">Trabajos</v-btn>
      <v-btn text @click="scrollTo('services')">Servicios</v-btn>
      <v-btn text @click="scrollTo('contact')">Contacto</v-btn>
    </v-app-bar>

    <!-- Banner principal -->
    <v-container fluid class="pa-0">
      <v-img
        src="@/assets/banner.jpg"
        height="450"
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
    <v-container id="about" class="text-center my-12">
      <h2 class="text-h4 mb-4">Sobre mí</h2>
      <p class="mx-auto" style="max-width: 700px;">
        Soy Licenciado en Seguridad e Higiene con experiencia en prevención de riesgos laborales,
        asesoramiento técnico y capacitaciones para empresas e instituciones.
        Mi objetivo es garantizar ambientes de trabajo seguros, saludables y eficientes
      </p>
    </v-container>

    <!-- Trabajos realizados -->
    <v-container id="projects" class="text-center my-12">
      <h2 class="text-h4 mb-4">Trabajos realizados</h2>
      <v-row>
        <v-col
          v-for="(trabajo, i) in trabajos"
          :key="i"
          cols="12"
          md="4"
        >
          <v-card class="mx-auto" max-width="400">
            <v-img :src="trabajo.img" height="350" cover></v-img>
            <v-card-title>{{ trabajo.titulo }}</v-card-title>
            <v-card-text>{{ trabajo.descripcion }}</v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>

    <!-- Servicios -->
    <v-container id="services" class="text-center my-12">
      <h2 class="text-h4 mb-4">Servicios</h2>
      <v-row>
        <v-col
          v-for="(servicio, i) in servicios"
          :key="i"
          cols="12"
          md="4"
        >
          <v-card class="mx-auto" max-width="400">
            <v-icon :icon="servicio.icon" size="80" color="#1565c0"></v-icon>
            <v-card-title>{{ servicio.titulo }}</v-card-title>
            <v-card-text>{{ servicio.descripcion }}</v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>

    <!-- Contacto -->
    <v-footer id="contact" color="blue-darken-4" class="white--text pa-10">
      <v-container>
        <v-row align="center" justify="center" class="text-center">
          <v-col cols="12" md="4">
            <p class="mb-2">📞 Teléfono: +54 9 3329 57-033</p>
            <a
              href="https://www.instagram.com/jmg_seguridadehigiene/"
              target="_blank"
              class="white--text text-decoration-none"
            >
              📷 Instagram: jmg_seguridadehigiene
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
        { 
          titulo: "Obra industrial", 
          descripcion: "Supervisión de condiciones de seguridad en planta.", 
          img: "/Obra industrial.png"
        },
        { 
          titulo: "Capacitaciones", 
          descripcion: "Charlas de seguridad laboral para empleados.", 
          img: "/Capacitaciones.png"
        },
        { 
          titulo: "Consultorías", 
          descripcion: "Asesoramiento en prevención de riesgos.", 
          img: "/Consultoria.png" 
        },
      ],
      servicios: [
        { 
          titulo: "Asesoramiento Integral", 
          descripcion: "Evaluaciones y planes de acción personalizados según las necesidades de tu empresa.", 
          icon: "mdi-shield-check"
        },
        { 
          titulo: "Capacitaciones Laborales", 
          descripcion: "Formación en seguridad, uso de elementos de protección y prevención de accidentes.", 
          icon: "mdi-file-document-check"
        },
        { 
          titulo: "Auditorías Técnicas", 
          descripcion: "Inspecciones y control del cumplimiento de normas de seguridad e higiene.", 
          icon: "mdi-school"
        },
      ]
    };
  }
};
</script>