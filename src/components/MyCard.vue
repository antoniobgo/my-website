<script setup>
import { defineProps, ref } from "vue";
import { useDisplay } from "vuetify";

const { mdAndUp } = useDisplay();
const props = defineProps(["cardContent", "index"]);
const index = ref(props.index);
const cardClasses =
  index.value === 0
    ? ref(["rounded-r-0", "rounded-l-xl"])
    : index.value === 1
    ? ref(["rounded-0"])
    : ref(["rounded-r-xl", "rounded-l-0"]);
const smallCardClasses =
  index.value === 0
    ? ref(["rounded-t-xl", "rounded-b-0"])
    : index.value === 1
    ? ref(["rounded-0", "rounded-0"])
    : ref(["rounded-b-xl", "rounded-t-0"]);
</script>
<template>
  <v-card class="rounded-xl" min-height="876" min-width="478">
    <v-card-title>
      <v-row>
        <v-col>
          <v-row class="pt-15 pb-5">
            <v-spacer />
            <v-icon color="primary" size="150" class="icon-size">
              {{ props.cardContent.icon }}
            </v-icon>
            <!-- <v-icon color="primary" class="icon-size"> mdi-cog-outline </v-icon> -->
            <v-spacer />
          </v-row>
          <v-row>
            <v-spacer />
            <p class="card-title">{{ props.cardContent.title }}</p>
            <v-spacer />
          </v-row>
        </v-col>
      </v-row>
    </v-card-title>
    <v-row justify="center" class="py-10">
      <p
        class="default-text text-center"
        style="color: rgb(var(--v-theme-primary))"
      >
        {{ props.cardContent.subtitle }}
      </p>
    </v-row>
    <v-row v-for="tool in props.cardContent.tools" :key="tool" justify="center">
      <p class="text-center subtitle-text pa-1">{{ tool }}</p>
    </v-row>
    <v-row v-if="props.cardContent.subTools" justify="center" class="pt-5 pb-3">
      <p
        class="default-text text-center"
        style="color: rgb(var(--v-theme-primary))"
      >
        Interesse em:
      </p>
    </v-row>
    <v-row
      v-for="subTool in props.cardContent.subTools"
      :key="subTool"
      justify="center"
    >
      <p class="subtitle-text text-center pa-1">
        {{ subTool }}
      </p>
    </v-row>
  </v-card>
</template>

<style>
.icon-size {
  font-size: 4em;
}
</style>
