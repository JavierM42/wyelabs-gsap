<template>
  <div id="app" class="p-8">
    <div class="h-16">
      <div v-if="showSquare" class="square w-16 h-16 bg-red-600" />
    </div>
    <div class="my-4 space-x-4">
      <button
        @click="showSquare = !showSquare"
        class="px-4 py-1 border border-red-500 bg-red-200 rounded-full hover:shadow-lg font-medium text-red-900"
      >
        Toggle the square
      </button>
    </div>
  </div>
</template>

<script>
import { gsap } from 'gsap';

export default {
  name: 'App',
  data() {
    return {
      showSquare: true
    };
  },
  methods: {
    animate() {
      this.tl.restart();
    }
  }
}
</script>
