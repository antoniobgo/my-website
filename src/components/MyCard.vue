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
console.log(index.value);
console.log(cardClasses);
console.log("-----");
//eslint-disable-next-line
</script>
<template>
  <v-card
    :class="mdAndUp ? [...cardClasses] : [...smallCardClasses]"
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
        <p
          class="default-text text-center"
          style="color: rgb(var(--v-theme-primary))"
        >
          {{ props.cardContent.subtitle }}
        </p>
      </v-row>
      <v-row
        v-for="tool in props.cardContent.tools"
        :key="tool"
        justify="center"
      >
        <p class="text-center subtitle-text pa-2">{{ tool }}</p>
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
        <p class="subtitle-text text-center pa-2">
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
