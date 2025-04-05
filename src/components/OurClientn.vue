<template>
  <div>
    <div class="flex pb-2">
      <div class="bg-star w-full h-6"></div>
      <div class="bg-che w-full h-6"></div>
      <div class="bg-black w-full h-6"></div>
    </div>
    <div class="flex py-4">
      <div
        class="font-roboto font-extrabold capitalize text-2xl sm:text-3xl md:text-4xl"
      >
        <div class="flex space-x-2">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="size-10 text-black"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="m11.25 11.25.041-.02a.75.75 0 0 1 1.063.852l-.708 2.836a.75.75 0 0 0 1.063.853l.041-.021M21 12a9 9 0 1 1-18 0 9 9 0 0 1 18 0Zm-9-3.75h.008v.008H12V8.25Z"
            />
          </svg>
          <h1>Klien Kami</h1>
        </div>
      </div>
    </div>

    <div class="overflow-hidden w-full py-4 relative">
      <div
        class="marquee whitespace-nowrap flex items-center space-x-20 animate-marquee"
      >
        <div
          v-for="(client, index) in clients"
          :key="index"
          class="flex items-center space-x-4"
        >
          <img
            :src="client.logo"
            alt="logo"
            class="max-w-16 max-h-16 lg:max-w-20 lg:max-h-20 grayscale"
          />
          <h1
            class="text-base sm:text-xl md:text-2xl font-roboto capitalize font-bold"
          >
            {{ client.nama }}
          </h1>
        </div>
        <div
          v-for="(client, index) in clients"
          :key="'dupe-' + index"
          class="flex items-center space-x-2"
        >
          <img
            :src="client.logo"
            alt="logo"
            class="max-w-16 max-h-16 lg:max-w-20 lg:max-h-20 grayscale"
          />
          <h1 class="text-base sm:text-xl md:text-2xl font-anton uppercase">
            {{ client.nama }}
          </h1>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      clients: [
        {
          nama: "Political Volunteer System",
          logo: require("../assets/bombs-2.png"),
        },
        {
          nama: "Online Travel Agent Booking System",
          logo: require("../assets/nusa.png"),
        },
        { nama: "News Portal System", logo: require("../assets/dnk.png") },
        { nama: "News Portal System", logo: require("../assets/bimakita.png") },
        {
          nama: "Lembaga Perlindungan Konsumen Nasional Indonesia",
          logo: require("../assets/lpkni.png"),
        },
      ],
    };
  },
};
</script>

<style scoped>
@keyframes marquee {
  0% {
    transform: translateX(0%);
  }
  100% {
    transform: translateX(-50%);
  }
}

.animate-marquee {
  animation: marquee 10s linear infinite;
}
</style>
