<template>
  <v-app>

    <v-app-bar
  color="#33691E"
  density="comfortable"
  dark
  flat
  class="px-2 px-sm-4"
>

  <!-- BLOQUE NOMBRE + LOGO (NO se estira, NO se centra, NO se corta) -->
  <v-toolbar-title class="pa-0 ma-0" style="flex: none;">
    <div style="display:inline-flex; align-items:center; gap:6px;">
      <span class="font-weight-bold text-white" style="font-size: clamp(1rem, 3vw, 1.2rem);">Juan Mateo Gutierrez</span>
      <v-img
        src="/logo.jpg"
        width="32"
        height="32"
        cover
        style="border-radius:50%;"
      />
    </div>
  </v-toolbar-title>

  <!-- MENU HAMBURGUESA EN CELU -->
  <v-spacer />
  <v-app-bar-nav-icon class="d-sm-none" @click="drawer = !drawer" />

  <!-- BOTONES NORMALES SOLO EN PANTALLA GRANDE (md y superior) -->
  <div class="d-none d-md-flex" style="gap:4px;">
    <v-btn href="#about" variant="text" size="small">Sobre mí</v-btn>
    <v-btn href="#services" variant="text" size="small">Servicios</v-btn>
    <v-btn href="#projects" variant="text" size="small">Trabajos realizados</v-btn>
    <v-btn href="#contact" variant="text" size="small">Contacto</v-btn>
  </div>

</v-app-bar>

<!-- MENU LATERAL PARA MOBILE -->
<v-navigation-drawer v-model="drawer" temporary>
  <v-list>
    <v-list-item href="#about" title="Sobre mí" />
    <v-list-item href="#services" title="Servicios" />
    <v-list-item href="#projects" title="Trabajos realizados" />
    <v-list-item href="#contact" title="Contacto" />
  </v-list>
</v-navigation-drawer>


    <!-- Banner principal -->
    <v-container class="hero" fluid>
  <h1>Juan Mateo Gutierrez</h1>
  <h2>Lic. en Seguridad e Higiene</h2>
</v-container>


    <!-- Sobre mí -->
    <v-container id="about" class="text-center my-12">
  <h3 class="about-title mb-4">Sobre mí</h3>
  <p class="about-text mx-auto" style="max-width: 800px;">
        <p>Soy Licenciado en Seguridad e Higiene con mas de 5 años de experiencia aplicada en los diferentes rubros como agro industria, salud, logística, obras, estaciones de servicio entre otros.
        </p>
        <p> Mi objetivo es garantizar ambientes de trabajo seguros, saludables y eficientes para mejorar la productividad de los trabajadores y de las organizaciones.</p>
       <p> Así como también cumplir con la normativa legal y exigencias de certificaciones.</p>
      </p>
    </v-container>

    <!-- Servicios -->
    <v-container id="services" class="text-center my-12">
      <h5 class="text-h4 mb-4">Servicios</h5>
      <v-row>
        <v-col
          v-for="(servicio, i) in servicios"
          :key="i"
          cols="12"
          sm="6"
          md="4"
        >
          <v-card class="mx-auto" style="max-width: 400px; width: 100%;">
            <v-icon :icon="servicio.icon" size="80" color="#1565c0"></v-icon>
            <v-card-title>{{ servicio.titulo }}</v-card-title>
            <v-card-text>{{ servicio.descripcion }}</v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>

    <!-- Trabajos realizados -->
    <v-container id="projects" class="text-center my-12">
      <h4 class="projects-title mb-4">Trabajos realizados</h4>
      <v-row>
        <v-col
          v-for="(trabajo, i) in trabajos"
          :key="i"
          cols="12"
          sm="6"
          md="4"
        >
          <v-card class="mx-auto" style="max-width: 400px; width: 100%;">
            <v-img :src="trabajo.img" height="350" cover></v-img>
            <v-card-title>{{ trabajo.titulo }}</v-card-title>
            <v-card-text>{{ trabajo.descripcion }}</v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>

    <!-- Contacto -->
    <v-footer id="contact" color="#33691E" class="white--text pa-6 pa-sm-10">
      <v-container>
        <v-row align="center" justify="center" class="text-center">
          <v-col cols="12" md="4">
            <p class="mb-2">📞 Teléfono: +54 9 3329 57-0339</p>
            <a
            href="https://www.instagram.com/jmg_seguridadehigiene/"
            target="_blank"
            style="color: white !important;"
            class="white--text text-decoration-none"
            >
              📷 Instagram: jmg_seguridadehigiene
            </a>
            <p class="mt-2">📍 San Pedro, Buenos Aires</p>
          </v-col>
        </v-row>
        <v-row justify="center" class="mt-4">
          <p class="text-caption">© {{ new Date().getFullYear() }} Juan Mateo Gutierrez - Todos los derechos reservados</p>
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
    icon: "mdi-account-cog" // Más acorde al asesoramiento
  },
  { 
    titulo: "Capacitaciones Laborales", 
    descripcion: "Formaciones teóricas y practicas de seguridad laboral basadas en el organigrama de cada empresa.", 
    icon: "mdi-school" // Icono de capacitación
  },
  { 
    titulo: "Auditorías Técnicas", 
    descripcion: "Inspecciones y control del cumplimiento de normas de Seguridad e Higiene.", 
    icon: "mdi-clipboard-check" // Control / auditoría
  },
]

    };
  }
};
</script>