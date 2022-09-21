<script setup>
import { defineProps, ref, computed } from "vue";

const props = defineProps(["portfolio"]);
const portfolio = ref(props.portfolio);
const techListString = computed(() => {
  let techListFormatted = "";
  for (let i = 0; i < portfolio.value.techList.length; i++) {
    if (i !== 0)
      techListFormatted =
        techListFormatted + " | " + portfolio.value.techList[i];
    else techListFormatted = portfolio.value.techList[i];
  }
  return techListFormatted;
});
</script>

<template>
  <div>
    <v-hover v-slot="{ isHovering, props }">
      <v-card height="313" v-bind="props">
        <div v-if="!isHovering" class="h-100">
          <v-row no-gutters dense class="h-100 card-color" align="center">
            <v-img
              class="logo-height"
              :src="require('../assets/' + portfolio.logo)"
            ></v-img>
          </v-row>
        </div>
        <div class="h-100 on-hover-card" v-else>
          <v-row no-gutters dense class="h-100" justify="center" align="center">
            <v-col cols="11" class="px-5">
              <p class="portfolio-card-text text-left pt-15">
                {{ portfolio.title }}
              </p>

              <p class="portfolio-card-subtitle-text py-3 text-left">
                Quer ver o repositório no GitHub?
              </p>
              <v-btn
                class="text-white github-button py-3 mx-2"
                size="small"
                :href="portfolio.repoAddress"
                >github</v-btn
              >

              <v-btn
                v-if="portfolio.link"
                class="text-white github-button py-3 mx-2"
                size="small"
                :href="portfolio.link"
                >visualizar site
              </v-btn>
            </v-col>
            <v-col cols="12">
              <v-row dense no-gutters justify="end">
                <p class="portfolio-card-tech-text pa-3 px-10">
                  {{ techListString }}
                </p>
              </v-row>
            </v-col>
          </v-row>
        </div>
      </v-card>
    </v-hover>
  </div>
</template>

<style>
.on-hover-card {
  background-color: #2f0d59;
}
.card-color {
  background-color: #dfdfdf;
}
.logo-height {
  height: 35%;
}
.portfolio-card {
  border-radius: 20px;
}
.portfolio-card-text {
  font-weight: 700;
  font-size: 1.25rem;
  line-height: 1.875rem;
  letter-spacing: 0.031rem;
  color: #fafafa;
}
.portfolio-card-subtitle-text {
  font-weight: 500;
  font-size: 1rem;
  line-height: 1.875rem;
  letter-spacing: 0.031rem;
  color: #fafafa;
}
.portfolio-card-tech-text {
  font-weight: 700;
  font-size: 0.875rem;
  line-height: 1.063rem;
  letter-spacing: 0.031rem;
  color: #fafafa;
}
.github-button {
  background-color: #7611f4;
}
</style>
