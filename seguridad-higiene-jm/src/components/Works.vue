<template>
  <v-container class="py-12">
    <h2 class="text-center mb-6">Trabajos Realizados</h2>
    <v-row>
      <v-col cols="12" md="4" v-for="i in 3" :key="i">
        <v-card>
          <v-img :src="'https://placehold.co/600x400?text=Trabajo+' + i" height="200px"></v-img>
          <v-card-text>
            <p>Descripción breve del trabajo realizado.</p>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
</script>