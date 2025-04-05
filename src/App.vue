<template>
  <div class="relative p-2 md:p-6">
    <MainPage @mousemove="handleMouseMove" :style="parallaxStyle" />
  </div>
</template>

<script>
import MainPage from "./views/MainPage.vue";

export default {
  name: "App",
  components: {
    MainPage,
  },
  data() {
    return {
      mouseX: 0,
      mouseY: 0,
    };
  },
  computed: {
    parallaxStyle() {
      const movementX = (this.mouseX - window.innerWidth / 2) / 50;
      const movementY = (this.mouseY - window.innerHeight / 2) / 50;
      return {
        transform: `translate(${movementX}px, ${movementY}px)`,
      };
    },
  },
  methods: {
    handleMouseMove(event) {
      this.mouseX = event.clientX;
      this.mouseY = event.clientY;
    },
  },
};
</script>
