<template>
  <div id="app" class="p-8">
    <div class="h-16">
      <transition :css="false" @leave="leave" @enter="enter">
        <div v-if="showSquare" class="square w-16 h-16 bg-red-600" />
        <div v-else class="circle w-16 h-16 bg-blue-600 rounded-full" />
      </transition>
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
    leave(element, done) {
      gsap.to(element, { duration: 0.4, autoAlpha: 0, scale: 0, ease: 'back.in', onComplete: done });
    },
    enter(element, done) {
      gsap.from(element, { duration: 0.4, yPercent: 100, autoAlpha: 0, ease: 'back.out', onComplete: done });
    }
  }
}
</script>
