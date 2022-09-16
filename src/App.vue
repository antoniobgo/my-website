<script setup>
import OnHoverButton from "./components/OnHoverButton.vue";
import router from "./router/index.js";
import { useDisplay } from "vuetify";

const { mdAndUp } = useDisplay();
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
      <template v-slot:prepend>
        <v-btn class="mt-5">
          <div
            @click="onLogoClick"
            :class="mdAndUp ? 'logo' : 'responsive-logo'"
          ></div>
        </v-btn>
      </template>
      <template v-slot:append>
        <v-btn
          id="contact-button"
          @click="onContactButtonClick"
          width="110"
          height="42"
          variant="outlined"
        >
          Contato
        </v-btn>
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
          <v-card-text class="text-white">
            {{ new Date().getFullYear() }} — <strong>Antonio Gomes</strong>
          </v-card-text>
        </v-card>
      </v-footer>
    </v-main>
  </v-app>
</template>

<style>
@font-face {
  font-family: downloadedInter;
  src: url("/src/fonts/Inter-VariableFont_slnt,wght.ttf");
}
#contact-button > .v-btn__content {
  font-weight: 500;
  font-size: 1rem;
  line-height: 1.21rem;
}
.my-app-bar {
  height: 5rem;
}
.logo {
  background: url("./assets/logo.svg") no-repeat;
  height: 4rem;
  width: 12rem;
}
.responsive-logo {
  background: url("./assets/logo.svg") no-repeat;
  height: 3rem;
  width: 6rem;
}
.app-font {
  font-family: downloadedInter, sans-serif;
}
.secondary-title-text {
  font-weight: 800;
  line-height: 2.25rem;
  font-size: 2rem;
  letter-spacing: 0.1rem;
}
.title-text {
  font-weight: 700;
  line-height: 6.429rem;
  font-size: 5.313rem;
  letter-spacing: 0.15rem;
}
.smaller-title-text {
  font-size: 1.4rem;
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
  font-weight: 500;
  line-height: 2.5rem;
  font-size: 1.5rem;
  letter-spacing: 0.125rem;
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
