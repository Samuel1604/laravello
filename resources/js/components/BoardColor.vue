<template>
  <div
    @click="$emit('changed', color)"
    :class="[colors[color]]"
    class="
      h-6
      w-6
      md:w-8
      md:h-8
      mr-1
      md:mr-2
      rounded-sm
      cursor-pointer
      flex
      justify-center
      items-center
      text-white text-xl
    "
  >
    <span v-if="activeColor == color">✓</span>
  </div>
</template>


<script>
import { colorMap500 } from "../Utils";
export default {
  props: {
    color: String,
    activeColor: String,
  },
  computed: {
    colors: () => colorMap500,
  },
};
</script>
