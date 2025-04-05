<template>
  <div class="font-Jet">
    <div class="flex">
      <div class="bg-star w-full h-6"></div>
      <div class="bg-che w-full h-6"></div>
      <div class="bg-black w-full h-6"></div>
    </div>

    <div class="w-full px-2 md:px-0 shadow-sm shadow-gray-200">
      <div class="flex flex-col md:flex-row items-center gap-6 md:gap-10">
        <div class="w-full md:flex-1 hidden sm:block">
          <img
            src="@/assets/server.jpg"
            alt="server"
            class="w-full h-[250px] md:h-full object-cover rounded-xl sm:rounded-none"
          />
        </div>

        <div
          class="bg-white w-full md:max-w-[600px] rounded-xl sm:rounded-none shadow-sm"
        >
          <div class="p-6 md:p-8">
            <div
              class="font-roboto font-extrabold tracking-wide text-2xl md:text-4xl lg:text-5xl mb-4"
            >
              <div class="flex items-center space-x-2">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke-width="1.5"
                  stroke="currentColor"
                  class="w-6 h-6 md:w-8 md:h-8 text-black"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    d="m11.25 11.25.041-.02a.75.75 0 0 1 1.063.852l-.708 2.836a.75.75 0 0 0 1.063.853l.041-.021M21 12a9 9 0 1 1-18 0 9 9 0 0 1 18 0Zm-9-3.75h.008v.008H12V8.25Z"
                  />
                </svg>
                <h1>Misi</h1>
              </div>
            </div>

            <div class="text-sm md:text-base font-sans font-medium">
              <Splide
                :options="{
                  type: 'slide',
                  perPage: 1,
                  arrows: true,
                  pagination: true,
                  gap: '1rem',
                  autoplay: true,
                  interval: 4000,
                  pauseOnHover: true,
                }"
              >
                <SplideSlide
                  v-for="(item, index) in texts"
                  :key="index"
                  class="px-2 py-4"
                >
                  <div>
                    <p class="text-black text-justify">{{ item }}</p>
                  </div>
                </SplideSlide>
              </Splide>
            </div>
          </div>
          <div class="w-full md:flex-1 block sm:hidden">
            <img
              src="@/assets/server.jpg"
              alt="server"
              class="w-full h-[250px] md:h-full object-cover rounded-xl sm:rounded-none"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { Splide, SplideSlide } from "@splidejs/vue-splide";
import "@splidejs/splide/dist/css/splide.min.css";

export default {
  components: {
    Splide,
    SplideSlide,
  },
  data() {
    return {
      texts: [
        `Lorem ipsum dolor sit, amet consectetur adipisicing elit. Harum
        provident corporis voluptatibus aspernatur ipsa perspiciatis?
        Itaque sapiente, illum maiores ex impedit ad libero laborum
        expedita temporibus deleniti ut animi sunt.`,
        `Lorem ipsum dolor sit, amet consectetur adipisicing elit. Harum
        provident corporis voluptatibus aspernatur ipsa perspiciatis?
        Itaque sapiente, illum maiores ex impedit ad libero laborum
        expedita temporibus deleniti ut animi sunt.`,
        `Lorem ipsum dolor sit, amet consectetur adipisicing elit. Harum
        provident corporis voluptatibus aspernatur ipsa perspiciatis?
        Itaque sapiente, illum maiores ex impedit ad libero laborum
        expedita temporibus deleniti ut animi sunt.`,
        `Lorem ipsum dolor sit, amet consectetur adipisicing elit. Harum
        provident corporis voluptatibus aspernatur ipsa perspiciatis?
        Itaque sapiente, illum maiores ex impedit ad libero laborum
        expedita temporibus deleniti ut animi sunt.`,
      ],
    };
  },
};
</script>
