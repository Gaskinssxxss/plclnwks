<template>
  <div class="font-Jet">
    <div class="flex">
      <div class="bg-star w-full h-6"></div>
      <div class="bg-che w-full h-6"></div>
      <div class="bg-black w-full h-6"></div>
    </div>
    <div class="w-full px-2 md:px-0 shadow-sm shadow-gray-200">
      <div class="flex flex-col md:flex-row items-center gap-6 md:gap-10">
        <div class="bg-white w-full md:max-w-[500px] rounded-xl shadow-sm">
          <div class="p-6 md:p-8">
            <div
              class="font-roboto font-extrabold tracking-wide text-2xl md:text-4xl lg:text-5xl"
            >
              <div class="flex items-center space-x-2 mb-4">
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
                <h1>Visi</h1>
              </div>
            </div>
            <div
              class="pt-0 sm:pt-2 text-sm md:text-base font-sans font-medium text-justify leading-relaxed"
            >
              <p>
                Lorem ipsum dolor sit, amet consectetur adipisicing elit. Harum
                provident corporis voluptatibus aspernatur ipsa perspiciatis?
                Itaque sapiente, illum maiores ex impedit ad libero laborum
                expedita temporibus deleniti ut animi sunt.
              </p>
            </div>
          </div>
        </div>
        <div class="w-full md:flex-1">
          <img
            src="@/assets/linux.jpg"
            alt="linux"
            class="w-full h-[250px] md:h-full object-cover rounded-xl md:rounded-none"
          />
        </div>
      </div>
    </div>
  </div>
</template>
