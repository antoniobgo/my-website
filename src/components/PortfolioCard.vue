<script setup>
import { defineProps, ref } from "vue";
const props = defineProps(["portfolio"]);
const portfolio = ref(props.portfolio);
// console.log(portfolio.value.title);
</script>

<template>
  <div>
    <v-hover v-slot="{ isHovering, props }">
      <v-card height="290" variant="outlined" v-bind="props">
        <div v-if="!isHovering" class="h-100">
          <v-row no-gutters dense class="h-100" align="center">
            <v-img
              :src="require('../assets/' + portfolio.logo)"
              contain
            ></v-img>
          </v-row>
        </div>
        <div class="h-100 on-hover-card" v-else>
          <v-row no-gutters dense class="h-100" justify="center" align="center">
            <v-col cols="11">
              <p class="text-white subtitle-text text-center">
                {{ portfolio.title }}
              </p>
              <v-row
                no-gutters
                dense
                justify="center"
                class="mt-5"
                align="center"
              >
                <p class="text-white pa-3">Quer ver o repositório no GitHub?</p>
                <v-btn
                  class="text-white bg-primary"
                  size="small"
                  :href="portfolio.repoAddress"
                  >github</v-btn
                >
              </v-row>
            </v-col>
            <v-col cols="12">
              <v-row dense no-gutters justify="center">
                <v-sheet
                  v-for="item in portfolio.techList"
                  :key="item"
                  variant="outlined"
                  class="ma-1 rounded-pill bg-primary"
                >
                  <p class="subtitle-card-text pa-3">{{ item }}</p>
                </v-sheet>
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
  background-color: #043f7a;
}
</style>
