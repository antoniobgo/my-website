<script setup>
import OnHoverButton from "../components/OnHoverButton.vue";
import MyCard from "../components/MyCard.vue";
import router from "../router/index.js";
import { ref } from "vue";

const rounded1 = ref("rounded-s-xl");
const rounded2 = ref("rounded-e-0");
const rounded3 = ref("rounded-e-xl");
const rounded4 = ref("rounded-s-0");

const quemSou = ref();
const oQueFaco = ref();
const portfolio = ref();

const cardContents = [
  {
    icon: "mdi-xml",
    title: "Front End",
    subtitle: "Linguagens e ferramentas",
    tools: [
      "Html",
      "Css",
      "Javascript",
      "Vue.js",
      "Vuetify",
      "Pinia",
      "Vscode",
    ],
    subTools: ["Pug", "React"],
    cardClasses: [rounded1, rounded2],
  },
  {
    icon: "mdi-cog-outline",
    title: "Back End",
    subtitle: "Linguagens e ferramentas",
    tools: [
      "Node.js",
      "Git",
      "banco de dados relacional",
      "APIs Rest",
      "Vscode",
    ],
    subTools: ["Ruby on Rails", "NoSQL", "Graphql"],
    cardClasses: [rounded4, rounded2],
  },
  {
    icon: "mdi-book-open-outline",
    title: "Interesses",
    subtitle: "Áreas de interesse",
    tools: ["Código limpo", "Padrões de projeto", "Metodologias ágeis"],
    cardClasses: [rounded3, rounded4],
  },
];
const onQuemSouClick = () => {
  quemSou.value.scrollIntoView({ behavior: "smooth" });
};
const onOQueFacoClick = () => {
  oQueFaco.value.scrollIntoView({ behavior: "smooth" });
};
const onPortfolioClick = () => {
  portfolio.value.scrollIntoView({ behavior: "smooth" });
};
</script>

<template>
  <div>
    <v-container class="home-container mt-10 pt-10">
      <v-row justify="space-between">
        <div @click="onQuemSouClick">
          <OnHoverButton content="quem sou" />
        </div>
        <div @click="onOQueFacoClick">
          <OnHoverButton content="o que faço" />
        </div>
        <div @click="onPortfolioClick">
          <OnHoverButton content="portfolio" />
        </div>
        <div @click="router.push({ name: 'contact' })">
          <OnHoverButton content="contato" />
        </div>
      </v-row>
      <v-row justify="center">
        <p class="title-text title-margin">Desenvolvedor Full-Stack</p>
      </v-row>
      <v-row justify="center">
        <p class="subtitle-text subtitle-margin">
          Gosto de ajudar a resolver problemas reais com simplicidade e
          qualidade.
        </p>
      </v-row>
      <div class="avatar-text-positioning">
        <v-row justify="center">
          <v-avatar size="235px" class="mb-10 avatar-container">
            <img :src="require('../assets/pic2.png')" />
          </v-avatar>
        </v-row>
        <v-row justify="center" class="bg-primary extend-card">
          <v-col align-self="center" cols="6" class="mb-30">
            <v-row no-gutters justify="center">
              <p ref="quemSou" class="text-h4 font-weight-bold">
                Olá, sou o Antônio. Prazer em te conhecer.
              </p>
            </v-row>
            <v-row justify="center" class="mt-5">
              <p class="card-text text-center">
                Sempre tive interesse pela área de desenvolvimento de software,
                começando meus estudos na área há 6 anos e desenvolvendo
                aplicações web de forma profissional há 3 anos. Sou apaixonado
                pelo que faço e tenho uma grande sede de conhecimento :)
              </p>
            </v-row>
          </v-col>
        </v-row>
      </div>
      <p style="position: relative; bottom: 15rem" ref="oQueFaco"></p>
      <v-row
        style="position: relative; bottom: 12rem"
        justify="center"
        no-gutters
      >
        <v-col v-for="content in cardContents" :key="content.title">
          <MyCard :cardContent="content" />
        </v-col>
      </v-row>
    </v-container>
    <v-row justify="center">
      <p class="secondary-title-text">Trabalhos Recentes</p>
    </v-row>
    <v-row class="my-10" justify="center">
      <p ref="portfolio" class="default-text">
        Aqui estão os últimos trabalhos que realizei. Gostaria de ver mais?
        <a href="#">Me mande uma mensagem!</a>
      </p>
    </v-row>
    <v-row class="my-10" justify="center">
      <v-col cols="8">
        <v-row>
          <v-col cols="4">
            <v-card height="290" variant="outlined">
              <v-img
                color="black"
                :src="require('../assets/felipe-logo.svg')"
                contain
                style="height: 100%"
              ></v-img>
            </v-card>
          </v-col>
          <v-col cols="4">
            <v-card height="290" variant="outlined">
              <v-img
                color="black"
                :src="require('../assets/felipe-logo.svg')"
                contain
                style="height: 100%"
              ></v-img>
            </v-card>
          </v-col>
          <v-col cols="4">
            <v-card height="290" variant="outlined">
              <v-img
                color="black"
                :src="require('../assets/felipe-logo.svg')"
                contain
                style="height: 100%"
              ></v-img>
            </v-card>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
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
  margin-top: 6rem;
}
.card-text {
  font-size: 1.25rem !important;
  font-weight: 300;
  line-height: 2rem;
  letter-spacing: 0.1em !important;
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
.title-margin {
  margin-top: 10rem;
}
.subtitle-margin {
  margin-top: 3rem;
}
/* .avatar-container {
  width: 20rem;

  height: 15rem;
} */
</style>
