<template>
  <transition name="appear">
    <div
      class="overlay fixed w-full h-full bg-black z-30 top-0 bottom-0 left-0"
      @click.self="$emit('closed')"
      v-if="show"
    >
      <div
        class="w-full h-full bg-transparent flex justify-center items-center"
        @click.self="$emit('closed')"
      >
        <div class="" :style="style" @click.self="$emit('closed')">
          <slot></slot>
        </div>
      </div>
    </div>
  </transition>
</template>


<script>
export default {
  props: {
    width: Number,
    height: Number,
    show: Boolean,
  },
  computed: {
    style() {
      return {
        width: `${this.width}px`,
        height: `${this.height}px`,
      };
    },
  },
};
</script>

<style scoped>
.overlay {
  background-color: rgba(0, 0, 0, 0.7);
}
</style>























 