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
        <v-btn class="mt-8 ml-8">
          <div
            @click="onLogoClick"
            :class="mdAndUp ? 'logo' : 'responsive-logo'"
          ></div>
        </v-btn>
      </template>
      <template v-slot:append>
        <v-btn
          id="contact-button"
          class="mt-8 mr-8"
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
  font-weight: 700;
  line-height: 1.563rem;
  font-size: 2.5rem;
}
.title-text {
  font-weight: 700;
  line-height: 6.429rem;
  font-size: 5.313rem;
  letter-spacing: 0.1rem;
}
.smaller-title-text {
  font-size: 1.313rem;
  font-weight: 700;
  line-height: 1.563rem;
}
.default-text {
  font-weight: 600;
  line-height: 2.063rem;
  font-size: 1.69rem;
  letter-spacing: 0.056rem;
}
.smaller-default-text {
  font-weight: 600;
  line-height: 1.1rem;
  font-size: 1rem;
  letter-spacing: 0.031rem;
}
.card-title {
  font-weight: 900;
  line-height: 3.75rem;
  font-size: 3.125rem;
  letter-spacing: 0.056rem;
}
.smaller-card-title {
  font-weight: 900;
  line-height: 2rem;
  font-size: 1.75rem;
  letter-spacing: 0.031rem;
}
.subtitle-text {
  font-weight: 500;
  line-height: 2.5rem;
  font-size: 1.5rem;
  letter-spacing: 0.125rem;
}
.smaller-subtitle-text {
  font-weight: 500;
  line-height: 1.313rem;
  font-size: 0.8rem;
  letter-spacing: 0.031rem;
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
