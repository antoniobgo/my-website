<script setup>
import OnHoverButton from "../components/OnHoverButton.vue";
import MyCard from "../components/MyCard.vue";
import PortfolioCard from "../components/PortfolioCard.vue";
import router from "../router/index.js";
import { ref } from "vue";
import { useDisplay } from "vuetify";

const { mdAndUp } = useDisplay();
const roundedLeft = ref("rounded-l-xl !important");
const roundedRight = ref("rounded-r-xl !important");
const roundedTop = ref("rounded-t-xl !important");
const roundedBottom = ref("rounded-b-xl !important");
const rounded6 = ref("rounded-b-0");
const rounded7 = ref("rounded-0");
const rounded8 = ref("rounded-t-0");

const quemSou = ref();
const oQueFaco = ref();
const portfolio = ref();
const curriculo = ref();

const jobs = [
  {
    title:
      "Desenvolvimento de um site pessoal próprio, servindo informações profissionais relevantes.",
    techList: ["Front-End", "Vue.js"],
    logo: "logo.svg",
    repoAddress: "https://github.com/antoniobgo/my-website",
  },
  {
    title:
      "Trabalho ainda em desenvolvimento. Criação de um site a partir de protótipos vindo do cliente",
    techList: ["Front-End", "Vue.js"],
    logo: "felipe-logo.svg",
    link: "https://felipe-website-1e521.web.app",
    repoAddress: "https://github.com/antoniobgo/felipe-website",
  },
];

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
  },
  {
    icon: "mdi-book-open-outline",
    title: "Interesses",
    subtitle: "Áreas de interesse",
    tools: ["Código limpo", "Padrões de projeto", "Metodologias ágeis"],
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
const onCurriculoClick = () => {
  curriculo.value.scrollIntoView({ behavior: "smooth" });
};
const onContactButtonClick = () => {
  router.push({ name: "contact" });
};
</script>

<template>
  <div>
    <v-container fluid class="pa-0 mt-16">
      <v-row dense no-gutters justify="center" align-self="center">
        <v-col cols="12" sm="12" md="6" lg="3">
          <v-row no-gutters dense justify="center">
            <OnHoverButton
              size="small"
              content="quem sou"
              :clickFunction="onQuemSouClick"
            />
          </v-row>
        </v-col>
        <v-col cols="12" sm="12" md="6" lg="3">
          <v-row no-gutters dense justify="center">
            <OnHoverButton
              size="small"
              content="o que faço"
              :clickFunction="onOQueFacoClick"
            />
          </v-row>
        </v-col>

        <v-col cols="12" sm="12" md="6" lg="3">
          <v-row no-gutters dense justify="center">
            <OnHoverButton
              size="small"
              content="portfolio"
              :clickFunction="onPortfolioClick"
            />
          </v-row>
        </v-col>
        <v-col cols="12" sm="12" md="6" lg="3">
          <v-row no-gutters dense justify="center">
            <OnHoverButton
              size="small"
              content="currículo"
              :clickFunction="onCurriculoClick"
            />
          </v-row>
        </v-col>
      </v-row>
      <v-row dense no-gutters justify="center">
        <v-col sm="10" xs="10" md="8" lg="8">
          <v-row justify="center">
            <p
              :class="mdAndUp ? 'title-text' : 'smaller-title-text'"
              class="title-margin"
            >
              Desenvolvedor Full-Stack
            </p>
          </v-row>
        </v-col>
      </v-row>
      <v-row no-gutters dense justify="center">
        <v-col cols="8">
          <p class="subtitle-text subtitle-margin text-center">
            Gosto de ajudar a resolver problemas reais com simplicidade e
            qualidade.
          </p>
        </v-col>
      </v-row>

      <div class="avatar-margin">
        <v-row no-gutters dense justify="center" align-self="center">
          <div
            class="bg-white rounded-border d-flex justify-center align-center"
          >
            <v-img
              class="bg-white"
              max-width="317"
              max-height="317"
              style="border-radius: 50% !important"
              :src="require('../assets/pic2.png')"
              cover
            ></v-img>
          </div>
        </v-row>
      </div>
      <div class="after-picture-area">
        <v-row
          no-gutters
          dense
          justify="center"
          :class="mdAndUp ? 'extend-card' : 'phone-extend-card'"
          class="bg-primary extend-card"
        >
          <v-col
            :align-self="mdAndUp ? 'center' : 'center'"
            cols="10"
            md="8"
            class="mb-30"
          >
            <v-row class="margin-intro-message" no-gutters justify="center">
              <p
                ref="quemSou"
                class="text-center"
                :class="mdAndUp ? 'text-h4' : 'smaller-title-text'"
              >
                Olá, sou o Antônio. Prazer em te conhecer.
              </p>
            </v-row>
            <v-row no-gutters dense justify="center" class="mt-5">
              <p
                class="text-center"
                :class="mdAndUp ? 'card-text' : 'smaller-card-text'"
              >
                Sempre tive interesse pela área de desenvolvimento de software,
                começando meus estudos na área há 6 anos e desenvolvendo
                aplicações web de forma profissional há 3 anos. Sou apaixonado
                pelo que faço e tenho uma grande sede de conhecimento :)
              </p>
            </v-row>
          </v-col>
        </v-row>
        <p style="position: relative; bottom: 15rem" ref="oQueFaco"></p>
        <v-row
          style="position: relative; bottom: 12rem"
          justify="center"
          no-gutters
          dense
          ><v-col cols="8" sm="11" xs="11" md="10">
            <v-row no-gutters dense justify="center">
              <v-col v-for="(content, index) in cardContents" :key="index">
                <MyCard :cardContent="content" :index="index" />
              </v-col>
            </v-row>
          </v-col>
        </v-row>
        <v-row justify="center">
          <p class="secondary-title-text">Trabalhos Recentes</p>
        </v-row>
        <v-row class="my-10" justify="center">
          <v-col cols="10" md="8">
            <p ref="portfolio" class="default-text text-center">
              Aqui estão os últimos trabalhos que realizei. Gostaria de ver
              mais?
              <a
                @click="onContactButtonClick"
                class="text-blue text-decoration-underline"
                >Me mande uma mensagem!</a
              >
            </p>
          </v-col>
        </v-row>
        <v-row class="my-10" justify="center">
          <v-col cols="11" md="9" lg="8">
            <v-row>
              <v-col cols="12" lg="4" md="6">
                <PortfolioCard :portfolio="jobs[0]" />
              </v-col>
              <v-col cols="12" lg="4" md="6">
                <PortfolioCard :portfolio="jobs[1]" />
              </v-col>
            </v-row>
          </v-col>
        </v-row>
        <v-row class="mb-10">
          <v-spacer />
          <v-spacer />
          <v-col cols="10" lg="6">
            <p ref="curriculo" class="default-text">
              Gostaria de ver meu currículo?
              <a
                href="https://drive.google.com/file/d/1C9gGqU7IoiTru6lEaU9W-2udX4reMxKT/view?usp=sharing"
                >Clique aqui.</a
              >
            </p>
          </v-col>
          <v-spacer />
        </v-row>
      </div>
    </v-container>
  </div>
</template>

<style scoped>
.margin-intro-message {
  margin-top: 150px;
}
.after-picture-area {
  position: relative;
  top: -160px;
  z-index: 0;
}
.rounded-border {
  min-height: 335px;
  min-width: 335px;
  border: solid black 1px;
  border-radius: 50%;
  z-index: 3;
}
.move-up {
  position: relative;
  bottom: 17.5vh;
}
.mb-30 {
  margin-bottom: 22vh;
}
.avatar-margin {
  margin-top: 6rem;
}
.card-text {
  font-size: 1.25rem !important;
  font-weight: 300;
  line-height: 2rem;
  letter-spacing: 0.1em !important;
  text-transform: none !important;
}
.smaller-card-text {
  font-size: 1rem !important;
  font-weight: 300;
  line-height: 1.4rem;
  letter-spacing: 0.1em !important;
  text-transform: none !important;
}
.avatar {
  width: 210px;
  height: 210px;
}
.full-width {
  width: 100vw;
}
.extend-card {
  width: 100%;
  height: 700px;
}
.phone-extend-card {
  width: 100%;
  height: 120vh;
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
