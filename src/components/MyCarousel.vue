<script setup>
import { ref } from "vue";
const projects = ref(["projeto 1", "projeto-2", "projeto-3"]);
</script>

<template>
  <v-row justify="center" class="mb-10">
    <p class="text-h4">Trabalhos Recentes</p>
  </v-row>
  <v-row justify="center">
    <v-card
      v-for="item in projects"
      variant="outlined"
      class="card-settings ma-5"
      :key="item"
    >
      <v-card-title>
        <h3>{{ item }}</h3>
      </v-card-title>
    </v-card>
  </v-row>
</template>

<style>
.card-settings {
  min-height: 30vh;
  min-width: 20vw;
}
</style>
