<template>
  <v-app>
    <v-app-bar flat class="text-primary">
      <v-row justify="space-around">
        <div>
          <h1 class="hmm">Antonio - Freelancer Developer</h1>
        </div>
        <div>
          <h2>Contato: 48 9 98585899</h2>
        </div>
      </v-row>
    </v-app-bar>
    <v-main>
      <router-view />
      <v-footer class="pa-0">
        <v-card
          elevation="0"
          rounded="0"
          width="100%"
          class="bg-primary text-center"
        >
          <v-card-text>
            <v-btn class="mx-4" icon="mdi-home" variant="plain"></v-btn>
            <v-btn class="mx-4" icon="mdi-email" variant="plain"></v-btn>
            <v-btn class="mx-4" icon="mdi-calendar" variant="plain"></v-btn>
          </v-card-text>

          <v-divider></v-divider>

          <v-card-text class="text-white">
            {{ new Date().getFullYear() }} — <strong>Antonio</strong>
          </v-card-text>
        </v-card>
      </v-footer>
    </v-main>
  </v-app>
</template>

<script setup></script>

<style>
.v-application {
  font-family: "Times New Roman";
}
</style>
