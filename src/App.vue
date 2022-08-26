<script setup>
import OnHoverButton from "./components/OnHoverButton.vue";
import router from "./router/index.js";

const onContactButtonClick = function () {
  router.push({ name: "contact" });
};
const onLogoClick = function () {
  router.push({ name: "home" });
};
</script>

<template>
  <v-app class="app-font">
    <v-app-bar absolute flat class="text-primary my-app-bar">
      <!-- <v-row justify="space-between" align="center">
        <v-btn class="mb-3 ml-16 h-100">
          <div @click="onLogoClick" class="logo"></div>
        </v-btn>
        <div @click="onContactButtonClick" class="mr-16">
          <OnHoverButton
            size="x-small"
            rounded="0"
            content="Mande uma mensagem"
          />
        </div>
      </v-row> -->
      <template v-slot:prepend>
        <v-btn class="">
          <div @click="onLogoClick" class="logo"></div>
        </v-btn>
      </template>
      <template v-slot:append>
        <v-btn size="small" variant="outlined"> Contato </v-btn>
        <!-- <div @click="onContactButtonClick">
          <OnHoverButton
            size="x-small"
            rounded="0"
            content="Mande uma mensagem"
          />
        </div> -->
      </template>
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

<style>
.my-app-bar {
  height: 5rem;
}
.logo {
  background: url("./assets/logo.png") no-repeat;
  height: 5rem;
  width: 15rem;
}
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
  line-height: 5rem;
  font-size: 4rem;
  letter-spacing: 0.15rem;
}
.titleText {
  font-weight: 800;
  line-height: 5rem;
  font-size: 4rem;
  letter-spacing: 0.15rem;
}
.smaller-title-text {
  font-size: 1.6rem;
  font-weight: 800;
  line-height: 2.5rem;
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
.subtitle-card-text {
  font-weight: 300;
  line-height: 1rem;
  font-size: 0.9rem;
  letter-spacing: 0.05rem;
}
.margin-right {
  margin-right: 2rem;
}
</style>
