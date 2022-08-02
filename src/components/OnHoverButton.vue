<script setup>
import { defineProps } from "vue";
// eslint-disable-next-line no-undef
const props = defineProps(["content"]);
</script>
<template>
  <v-hover v-slot="{ props, isHovering }">
    <v-btn
      variant="outlined"
      size="x-large"
      rounded="pill"
      :class="{
        'bg-primary': isHovering,
        'text-white': isHovering,
        'text-primary': !isHovering,
      }"
      v-bind="props"
    >
      {{ content }}
    </v-btn>
  </v-hover>
</template>
