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
    title: "Criação de uma aplicação gerenciadora de tarefas.",
    techList: ["FullStack", "Vue.js", "Rails"],
    logo: "done.svg",
    link: "https://tobdone-3a16b.web.app/",
    repoAddress: "https://github.com/antoniobgo/2BDone",
  },
  {
    title:
      "Desenvolvimento de um site pessoal próprio, servindo informações profissionais relevantes.",
    techList: ["Front-End", "Vue.js"],
    logo: "logo.svg",
    repoAddress: "https://github.com/antoniobgo/my-website",
  },
  {
    title:
      "Criação de um site do tipo portfólio para um profissional da área de design",
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
      "Banco de dados relacional",
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
              content="linkedin"
              :clickFunction="onCurriculoClick"
            />
          </v-row>
        </v-col>
      </v-row>
      <v-row dense no-gutters justify="center">
        <v-col sm="11" xs="11" md="10">
          <v-row justify="center">
            <p
              :class="mdAndUp ? 'title-text' : 'smaller-title-text'"
              class="title-margin"
            >
              Desenvolvedor FullStack
            </p>
          </v-row>
        </v-col>
      </v-row>
      <v-row no-gutters dense justify="center">
        <v-col cols="8">
          <p
            :class="
              mdAndUp
                ? 'subtitle-text subtitle-margin text-center'
                : 'smaller-subtitle-text subtitle-margin text-center'
            "
          >
            Gosto de ajudar a resolver problemas reais com simplicidade e
            qualidade.
          </p>
        </v-col>
      </v-row>

      <div class="avatar-margin">
        <v-row no-gutters dense justify="center" align-self="center">
          <div
            class="bg-white d-flex justify-center align-center"
            :class="mdAndUp ? 'rounded-border' : 'smaller-rounded-border'"
          >
            <v-img
              class="bg-white"
              :max-width="mdAndUp ? '317' : '180'"
              :max-height="mdAndUp ? '317' : '180'"
              style="border-radius: 50% !important"
              :src="require('../assets/pic2.png')"
              cover
            ></v-img>
          </div>
        </v-row>
      </div>
      <div
        :class="mdAndUp ? 'after-picture-area' : 'after-smaller-picture-area'"
      >
        <div
          :class="mdAndUp ? 'extend-card' : 'phone-extend-card'"
          class="bg-primary extend-card"
        >
          <v-row justify="center">
            <v-col
              cols="11"
              :class="
                mdAndUp
                  ? 'margin-intro-message'
                  : 'smaller-margin-intro-message'
              "
            >
              <v-row justify="center">
                <p
                  ref="quemSou"
                  class="text-center"
                  :class="
                    mdAndUp
                      ? 'secondary-title-text py-5'
                      : 'smaller-title-text py-2'
                  "
                >
                  Olá, sou o Antônio.
                </p>
              </v-row>
              <v-row justify="center">
                <p
                  ref="quemSou"
                  class="text-center"
                  :class="
                    mdAndUp
                      ? 'secondary-title-text py-5'
                      : 'smaller-title-text py-2'
                  "
                >
                  Prazer em te conhecer.
                </p>
              </v-row>
            </v-col>
            <v-col cols="9" md="6">
              <v-row justify="center">
                <p
                  class="text-center pt-7"
                  :class="mdAndUp ? 'subtitle-text' : 'smaller-card-text'"
                >
                  Sempre tive interesse pela área de desenvolvimento de
                  software, começando meus estudos na área há 6 anos e
                  desenvolvendo aplicações web de forma profissional há 3 anos.
                  Sou apaixonado pelo que faço e tenho uma grande sede de
                  conhecimento :)
                </p>
              </v-row>
            </v-col>
          </v-row>
        </div>
        <p style="position: relative; bottom: 15rem" ref="oQueFaco"></p>
        <div style="position: relative; bottom: 15rem">
          <v-row justify="center" no-gutters dense
            ><v-col cols="8" sm="11" xs="11" md="10">
              <v-row no-gutters dense justify="center">
                <v-col
                  v-for="(content, index) in cardContents"
                  :key="index"
                  cols="12"
                  md="4"
                >
                  <MyCard
                    :class="mdAndUp ? 'mx-4' : 'mx-0 px-0 my-5'"
                    :cardContent="content"
                    :index="index"
                  />
                </v-col>
              </v-row>
            </v-col>
          </v-row>
          <v-row justify="center" class="title-margin">
            <p class="secondary-title-text">Trabalhos Recentes</p>
          </v-row>
          <v-row class="my-10" justify="center">
            <v-col cols="10" md="8">
              <p ref="portfolio" class="subtitle-text text-center">
                Aqui estão os últimos trabalhos que realizei. Gostaria de ver
                mais?
                <v-row class="mt-7" justify="center">
                  <v-btn
                    variant="outlined"
                    class="text-primary message-button"
                    @click="onContactButtonClick"
                  >
                    Me envie uma mensagem
                  </v-btn>
                </v-row>
              </p>
            </v-col>
          </v-row>
          <v-row class="my-10" justify="center">
            <v-col cols="12" md="3">
              <PortfolioCard :portfolio="jobs[0]" />
            </v-col>
            <v-col cols="12" md="3">
              <PortfolioCard :portfolio="jobs[1]" />
            </v-col>
            <v-col cols="12" md="3">
              <PortfolioCard :portfolio="jobs[2]" />
            </v-col>
          </v-row>
          <v-row
            no-gutters
            dense
            class="curriculo-card-margin"
            justify="center"
          >
            <v-col cols="11" lg="8">
              <v-card class="curriculo-card" height="370" elevation="2">
                <div class="h-100">
                  <v-row no-gutters dense class="h-100">
                    <v-col cols="12" align-self="center">
                      <v-row justify="center">
                        <p ref="curriculo" class="secondary-title-text mb-10">
                          LinkedIn
                        </p>
                      </v-row>
                      <v-row no-gutters dense justify="center">
                        <p class="subtitle-text text-center mb-10">
                          Para conhecer mais o meu trabalho e minha carreira:
                        </p>
                      </v-row>
                      <v-row justify="center">
                        <v-btn
                          height="44"
                          width="290"
                          color="primary"
                          variant="outlined"
                          href="https://linkedin.com/in/antonio-gomes-dev"
                        >
                          Acesse meu LinkedIn
                        </v-btn>
                      </v-row>
                    </v-col>
                  </v-row>
                </div>
              </v-card>
            </v-col>
          </v-row>
        </div>
      </div>
    </v-container>
  </div>
</template>

<style scoped>
.margin-intro-message {
  margin-top: 220px;
}
.smaller-margin-intro-message {
  margin-top: 150px;
}
.after-picture-area {
  position: relative;
  top: -160px;
  z-index: 0;
}
.after-smaller-picture-area {
  position: relative;
  top: -90px;
  z-index: 0;
}
.rounded-border {
  min-height: 335px;
  min-width: 335px;
  border: solid black 1px;
  border-radius: 50%;
  z-index: 3;
}
.smaller-rounded-border {
  min-height: 192px;
  min-width: 192px;
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
  margin-top: 3rem;
}
.card-text {
  font-size: 1.25rem !important;
  font-weight: 300;
  line-height: 2rem;
  letter-spacing: 0.1em !important;
  text-transform: none !important;
}
.smaller-card-text {
  font-size: 1rem;
  font-weight: 300;
  line-height: 1.4rem;
  letter-spacing: 0.1em !important;
  text-transform: none !important;
}
.smaller-subtitle-text {
  font-size: 0.94rem;
  line-height: 1.375rem;
  font-weight: 500;
  letter-spacing: 0.031rem;
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
  height: 850px;
}
.phone-extend-card {
  width: 100%;
  height: 110vh;
}
.title-margin {
  margin-top: 10rem;
}
.subtitle-margin {
  margin-top: 1.5rem;
}
.message-button {
  min-height: 43px;
  min-width: 286px;
}
.curriculo-card {
  border-radius: 15px;
  background-color: #fafafa;
}
.curriculo-card-margin {
  padding-top: 130px;
}
</style>
