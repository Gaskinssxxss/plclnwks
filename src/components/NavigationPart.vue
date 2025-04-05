<template>
  <div class="relative w-full">
    <div class="flex justify-between items-center px-0 sm:px-4 py-2">
      <div class="flex space-x-0 sm:space-x-4 items-center">
        <img
          class="w-16 h-16 md:w-14 md:h-14"
          src="@/assets/logos.png"
          alt="logo"
        />
        <div class="tracking-wide">
          <div class="bg-black">
            <h1 class="text-che text-lg md:text-2xl lg:text-4xl px-2 py-1">
              POLLACHEIAL
            </h1>
          </div>
          <h1 class="text-sm md:text-lg lg:text-xl">
            NETWORK <span>TECH.</span>
          </h1>
        </div>
      </div>

      <div class="hidden md:flex space-x-10 text-lg lg:text-xl font-medium">
        <a
          v-for="(item, index) in navItems"
          :key="index"
          :href="'#' + item.id"
          @click="scrollTo(item.id)"
          class="hover:underline font-roboto transition duration-200"
        >
          {{ item.label }}
        </a>
      </div>

      <button @click="toggleMenu" class="md:hidden">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="2.5"
          stroke="currentColor"
          class="w-8 h-8"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"
          />
        </svg>
      </button>
    </div>

    <transition name="fade">
      <div
        v-if="menuOpen"
        class="md:hidden absolute right-4 mt-2 bg-white border shadow-md rounded-md z-50 w-[85vw] max-w-[400px] text-black text-lg"
      >
        <a
          v-for="(item, index) in navItems"
          :key="index"
          :href="'#' + item.id"
          @click="scrollTo(item.id)"
          class="block py-2 hover:bg-gray-100 text-center font-roboto font-medium border-b last:border-b-0"
        >
          {{ item.label }}
        </a>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  data() {
    return {
      menuOpen: false,
      navItems: [
        { id: "about", label: "Tentang" },
        { id: "visi", label: "Visi & Misi" },
        { id: "services", label: "Layanan" },
        { id: "clients", label: "Klien" },
        { id: "footer", label: "Hubungi" },
      ],
    };
  },
  methods: {
    toggleMenu() {
      this.menuOpen = !this.menuOpen;
    },
    scrollTo(id) {
      const el = document.getElementById(id);
      if (el) {
        const y = el.getBoundingClientRect().top + window.pageYOffset - 100;
        window.scrollTo({ top: y, behavior: "smooth" });
      }
      this.menuOpen = false;
    },
  },
};
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>

<!-- <template>
  <div class="relative">
    <div class="flex justify-between items-center">
      <div class="flex space-x-4 items-center">
        <img class="w-14 h-14" src="@/assets/logos.png" alt="logo" />
        <div class="text-4xl tracking-wider">
          <div class="bg-black">
            <h1 class="text-che px-2 py-1">POLLACHEIAL</h1>
          </div>
          <h1 class="text-xl">NETWORK <span>TECH.</span></h1>
        </div>
      </div>

      <button @click="toggleMenu">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="2.5"
          stroke="currentColor"
          class="size-10"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"
          />
        </svg>
      </button>
    </div>

    <transition name="fade">
      <div
        v-if="menuOpen"
        class="absolute right-0 bg-white border shadow-md rounded-md z-50 w-[400px] text-black text-2xl"
      >
        <a
          v-for="(item, index) in navItems"
          :key="index"
          :href="'#' + item.id"
          @click="scrollTo(item.id)"
          class="block py-1 hover:bg-gray-100 space-y-2 text-center font-roboto font-medium shadow-sm shadow-black"
        >
          {{ item.label }}
        </a>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  data() {
    return {
      menuOpen: false,
      navItems: [
        { id: "about", label: "Tentang" },
        { id: "visi", label: "Visi & Misi" },
        { id: "services", label: "Layanan" },
        { id: "clients", label: "Klien" },
        { id: "footer", label: "Hubungi" },
      ],
    };
  },
  methods: {
    toggleMenu() {
      this.menuOpen = !this.menuOpen;
    },
    scrollTo(id) {
      const el = document.getElementById(id);
      if (el) {
        const y = el.getBoundingClientRect().top + window.pageYOffset - 100;
        window.scrollTo({ top: y, behavior: "smooth" });
      }
      this.menuOpen = false;
    },
  },
};
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style> -->
