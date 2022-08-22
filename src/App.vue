<template>
  <v-app class="app-font">
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
.app-font {
  font-family: Alata, sans-serif;
}
.secondary-title-text {
  font-weight: 800;
  line-height: 2.25rem;
  font-size: 2rem;
  letter-spacing: 0.1rem;
}
.title-text {
  font-weight: 800;
  line-height: 3.4rem;
  font-size: 4rem;
  letter-spacing: 0.15rem;
}
.default-text {
  font-weight: 300;
  line-height: 1.875rem;
  font-size: 1.5rem;
  letter-spacing: 0.01rem;
}
.card-title {
  font-weight: 800;
  line-height: 1.8rem;
  font-size: 2rem;
  letter-spacing: 0.01rem;
}
.subtitle-text {
  font-weight: 300;
  line-height: 1.6rem;
  font-size: 1.2rem;
  letter-spacing: 0.05rem;
}
</style>
