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
      id="main-button"
      class="ma-3"
      @click="clickFunction"
      variant="outlined"
      height="55"
      width="255"
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

<style>
#main-button > .v-btn__content {
  font-weight: 700;
  font-size: 1.125rem;
  line-height: 1.361rem;
}
</style>
