<script setup>
import { defineProps, ref } from "vue";
// eslint-disable-next-line no-undef
const props = defineProps({
  size: String,
  content: String,
  rounded: String,
  clickFunction: Function,
});
const size = props.size ? ref(props.size) : undefined;
const rounded = props.rounded ? ref(props.rounded) : undefined;
const clickFunction = props.clickFunction
  ? ref(props.clickFunction)
  : undefined;
</script>
<template>
  <v-hover v-slot="{ props, isHovering }">
    <v-btn
      @click="clickFunction"
      variant="outlined"
      size="large"
      :rounded="rounded ? rounded : 'pill'"
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
