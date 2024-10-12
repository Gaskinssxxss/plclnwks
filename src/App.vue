<template>
  <MainPage @mousemove="handleMouseMove" :style="parallaxStyle" />
</template>

<script>
import MainPage from "./views/MainPage.vue"

export default {
  name: 'App',
  components: {
    MainPage
  },
  data() {
    return {
      mouseX: 0,
      mouseY: 0,
      isLoading: true,
    }
  },
  computed: {
    parallaxStyle() {
      const movementX = (this.mouseX - window.innerWidth / 2) / 50;
      const movementY = (this.mouseY - window.innerHeight / 2) / 50;
      return {
        transform: `translate(${movementX}px, ${movementY}px)`
      };
    },
  },
  methods: {
    onLoadingComplete() {
      this.isLoading = false;
    },
    handleMouseMove(event) {
      this.mouseX = event.clientX;
      this.mouseY = event.clientY;
    }
  },
}
</script>
