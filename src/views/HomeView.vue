<script setup>
import OnHoverButton from "../components/OnHoverButton.vue";
import MyCard from "../components/MyCard.vue";
import { ref } from "vue";

const rounded1 = ref("rounded-s-xl");
const rounded2 = ref("rounded-e-0");
const rounded3 = ref("rounded-e-xl");
const rounded4 = ref("rounded-s-0");

const cardContents = [
  {
    icon: "mdi-xml",
    title: "Front End",
    subtitle: "Linguagens e ferramentas",
    tools: ["html", "css", "javascript", "vue.js", "vuetify", "vscode"],
    subTools: ["pug", "react"],
    cardClasses: [rounded1, rounded2],
  },
  {
    icon: "mdi-cog-outline",
    title: "Back End",
    subtitle: "Linguagens e ferramentas",
    tools: [
      "node.js",
      "git",
      "banco de dados relacional",
      "APIs Rest",
      "vscode",
    ],
    subTools: ["ruby on rails", "NoSQL", "graphql"],
    cardClasses: [rounded4, rounded2],
  },
  {
    icon: "mdi-book-open-outline",
    title: "Interesses",
    subtitle: "Áreas de interesse",
    tools: ["Código limpo", "Padrões de projeto", "metodologias ágeis"],
    cardClasses: [rounded3, rounded4],
  },
];
</script>

<template>
  <div>
    <v-container class="home-container mt-10 pt-10">
      <v-row justify="space-between">
        <OnHoverButton content="quem sou" />
        <OnHoverButton content="o que faço" />
        <OnHoverButton content="portfolio" />
        <OnHoverButton content="contato" />
      </v-row>
      <div class="avatar-text-positioning">
        <v-row justify="center">
          <v-avatar size="256" class="mb-10">
            <v-img :src="require('../assets/avatar.jpeg')" class="my-3" />
          </v-avatar>
        </v-row>
        <v-row justify="center" class="bg-primary extend-card">
          <v-col align-self="center" cols="6" class="mb-30">
            <v-row no-gutters justify="center">
              <p class="text-h4 font-weight-bold">
                Olá, sou o Antônio. Prazer em te conhecer.
              </p>
            </v-row>
            <v-row justify="center" class="mt-5">
              <p class="card-text text-center">
                Sempre tive interesse pela área de desenvolvimento de software e
                desenvolvo aplicações web há 3 anos.
              </p>
            </v-row>
          </v-col>
        </v-row>
      </div>
      <v-row justify="center" no-gutters>
        <v-col v-for="content in cardContents" :key="content.title">
          <MyCard :cardContent="content" />
        </v-col>
      </v-row>
    </v-container>
    <v-container>
      <MyCarousel />
    </v-container>
  </div>
</template>

<style scoped>
.move-up {
  position: relative;
  bottom: 17.5vh;
}
.mb-30 {
  margin-bottom: 22vh;
}
.avatar-text-positioning {
  margin-top: 25vh;
}
.card-text {
  font-size: 1.25rem !important;
  font-weight: 300;
  line-height: 2rem;
  letter-spacing: 0.03125em !important;
  font-family: "Roboto", sans-serif !important;
  text-transform: none !important;
}
.home-container {
  width: 60vw;
}
.avatar {
  width: 210px;
  height: 210px;
}
.full-width {
  width: 100vw;
}
.extend-card {
  margin-left: -21.5vw;
  margin-right: -21.5vw;
  height: 65vh;
}
</style>
