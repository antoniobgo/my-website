<script setup>
import { defineProps, ref } from "vue";
// eslint-disable-next-line no-undef
const props = defineProps({
  size: String,
  content: String,
  rounded: String,
});
const size = props.size ? ref(props.size) : undefined;
const rounded = props.rounded ? ref(props.rounded) : undefined;
</script>
<template>
  <v-hover v-slot="{ props, isHovering }">
    <v-btn
      variant="outlined"
      :size="size ? size.value : 'x-large'"
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
