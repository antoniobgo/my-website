<script setup>
import { defineProps } from "vue";
const props = defineProps(["cardContent"]);

// console.log(props.cardContent.cardClasses[1]);
console.log(props.cardContent.cardClasses[0]);
</script>
<template>
  <v-card
    :class="[
      props.cardContent.cardClasses[0].value,
      props.cardContent.cardClasses[1].value,
    ]"
    style="position: relative; bottom: 17.5vh"
    min-height="600"
  >
    <v-card-title>
      <v-row>
        <v-col>
          <v-row class="pa-15">
            <v-spacer />
            <v-icon color="primary" class="icon-size">
              {{ props.cardContent.icon }}
            </v-icon>
            <!-- <v-icon color="primary" class="icon-size"> mdi-cog-outline </v-icon> -->
            <v-spacer />
          </v-row>
          <v-row class="pb-10">
            <v-spacer />
            <p class="text-h4">{{ props.cardContent.title }}</p>
            <v-spacer />
          </v-row>
        </v-col>
      </v-row>
    </v-card-title>
    <v-card-text>
      <v-row justify="center" class="py-10">
        <p class="text-subtitle-1">{{ props.cardContent.subtitle }}</p>
      </v-row>
      <v-row
        v-for="tool in props.cardContent.tools"
        :key="tool"
        justify="center"
      >
        <p class="text-subtitle-1">{{ tool }}</p>
      </v-row>
    </v-card-text>
  </v-card>
</template>

<style>
.icon-size {
  font-size: 4em;
}
</style>
