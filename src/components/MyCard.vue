<script setup>
import { defineProps } from "vue";
const props = defineProps(["cardContent"]);
</script>
<template>
  <v-card
    :class="[
      props.cardContent.cardClasses[0].value,
      props.cardContent.cardClasses[1].value,
    ]"
    min-height="700"
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
            <p class="card-title">{{ props.cardContent.title }}</p>
            <v-spacer />
          </v-row>
        </v-col>
      </v-row>
    </v-card-title>
    <v-card-text>
      <v-row justify="center" class="py-5">
        <p class="default-text" style="color: rgb(var(--v-theme-primary))">
          {{ props.cardContent.subtitle }}
        </p>
      </v-row>
      <v-row
        v-for="tool in props.cardContent.tools"
        :key="tool"
        justify="center"
      >
        <p class="default-text pa-2">{{ tool }}</p>
      </v-row>
      <v-row
        v-if="props.cardContent.subTools"
        justify="center"
        class="pt-5 pb-3"
      >
        <p
          class="default-text text-center"
          style="color: rgb(var(--v-theme-primary))"
        >
          Também tenho interesse em:
        </p>
      </v-row>
      <v-row
        v-for="subTool in props.cardContent.subTools"
        :key="subTool"
        justify="center"
      >
        <p class="default-text pa-1">
          {{ subTool }}
        </p>
      </v-row>
    </v-card-text>
  </v-card>
</template>

<style>
.icon-size {
  font-size: 4em;
}
</style>
