<template>
  <div id="app" class="p-8">
    <div class="square w-16 h-16 bg-red-600" />
    <div class="my-4 space-x-4">
      <button
        @click="animate"
        class="px-4 py-1 border border-red-500 bg-red-200 rounded-full hover:shadow-lg font-medium text-red-900"
      >
        Animate me
      </button>
    </div>
  </div>
</template>

<script>
import { gsap } from 'gsap';

export default {
  name: 'App',
  methods: {
    animate() {
      gsap.to('.square', { duration: .2, x: 300 });
      gsap.to('.square', { duration: .2, x: 300, y: 300, delay: .2 });
      gsap.to('.square', { duration: .2, x: 0, y: 300, delay: .4 });
      gsap.to('.square', { duration: .2, x: 0, y: 0, delay: .6 });
    }
  }
}
</script>
