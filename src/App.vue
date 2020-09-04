<template>
  <div id="app" class="p-8">
    <div class="flex space-x-2">
      <div class="square w-16 h-16 bg-red-600" />
      <div class="square w-16 h-16 bg-red-600" />
      <div class="square w-16 h-16 bg-red-600" />
      <div class="square w-16 h-16 bg-red-600" />
    </div>
    <div class="my-4 space-x-4">
      <button
        @click="animate"
        class="px-4 py-1 border border-red-500 bg-red-200 rounded-full hover:shadow-lg font-medium text-red-900"
      >
        Animate me
      </button>
      <button
        @click="animateBack"
        class="px-4 py-1 border border-blue-500 bg-blue-200 rounded-full hover:shadow-lg font-medium text-blue-900"
      >
        Take me back
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
      gsap.to('.square', { duration: 1, opacity: 0.5, x: 300, rotation: 360, scale: 2, ease: 'back.inOut', stagger: 0.1 });
    },
    animateBack() {
      gsap.to('.square', { duration: 1, opacity: 1, x: 0, rotation: 0, scale: 1, ease: 'bounce.out', stagger: 0.5 });
    }
  }
}
</script>
