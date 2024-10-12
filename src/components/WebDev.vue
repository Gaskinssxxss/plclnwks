<template>
    <div class="py-4 px-4 sm:px-8 md:px-10">
        <div class="font-anton uppercase text-2xl sm:text-3xl md:text-4xl flex justify-between">
            <div>
                <h1>DevFlow...</h1>
            </div>
            <div>
                <button v-if="up" @click="open">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                        stroke="currentColor" class="size-10 hover:scale-125">
                        <path stroke-linecap="round" stroke-linejoin="round" d="m19.5 8.25-7.5 7.5-7.5-7.5" />
                    </svg>
                </button>
                <button v-if="down" @click="close">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                        stroke="currentColor" class="size-10 hover:scale-125">
                        <path stroke-linecap="round" stroke-linejoin="round" d="m4.5 15.75 7.5-7.5 7.5 7.5" />
                    </svg>
                </button>
            </div>
        </div>
        <div v-if="show" class="font-anton uppercase text-base sm:text-xl md:text-2xl">
            <div class="space-y-4 pt-4">
                <h1 class="border-b-2 border-black">Product Design</h1>
                <h1 class="border-b-2 border-black">flow Development</h1>
                <h1 class="border-b-2 border-black">Architecture info</h1>
                <h1 class="border-b-2 border-black">tech-storming</h1>
                <h1 class="border-b-2 border-black">Development</h1>
                <h1 class="border-b-2 border-black">Code testing</h1>
                <h1 class="border-b-2 border-black">Security testing</h1>
                <h1 class="border-b-2 border-black">Production</h1>
                <h1 class="border-b-2 border-black">SEO optimization</h1>
                <h1 class="border-b-2 border-black">Documentation</h1>
                <h1 class="border-b-2 border-black">Maintenance</h1>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            show: false,
            up: true,
            down: false
        }
    },
    methods: {
        open() {
            this.show = true;
            this.up = false;
            this.down = true;
        },
        close() {
            this.show = false;
            this.up = true;
            this.down = false;
        }
    },
}
</script>


<!-- <template>
    <div class="py-4 px-10">
        <div class="font-anton uppercase text-4xl flex justify-between">
            <div>
                <h1>
                    DevFlow...
                </h1>
            </div>
            <div>
                <button v-if="up" @click="open">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                        stroke="currentColor" class="size-10 hover:scale-125">
                        <path stroke-linecap="round" stroke-linejoin="round" d="m19.5 8.25-7.5 7.5-7.5-7.5" />
                    </svg>
                </button>
                <button v-if="down" @click="close">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                        stroke="currentColor" class="size-10 hover:scale-125">
                        <path stroke-linecap="round" stroke-linejoin="round" d="m4.5 15.75 7.5-7.5 7.5 7.5" />
                    </svg>
                </button>
            </div>
        </div>
        <div v-if="show" class="font-anton uppercase text-xl">
            <div class="space-y-4 pt-4">
                <h1 class="border-b-2 border-black">Product Design</h1>
                <h1 class="border-b-2 border-black">flow Development</h1>
                <h1 class="border-b-2 border-black">Architecture info</h1>
                <h1 class="border-b-2 border-black">tech-storming</h1>
                <h1 class="border-b-2 border-black">Development</h1>
                <h1 class="border-b-2 border-black">Code testing</h1>
                <h1 class="border-b-2 border-black">Security testing</h1>
                <h1 class="border-b-2 border-black">Production</h1>
                <h1 class="border-b-2 border-black">SEO optimization</h1>
                <h1 class="border-b-2 border-black">Documentation</h1>
                <h1 class="border-b-2 border-black">Maintenance</h1>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            show: false,
            up: true,
            down: false
        }
    },
    methods: {
        open() {
            this.show = true;
            this.up = false;
            this.down = true;
        },
        close() {
            this.show = false;
            this.up = true;
            this.down = false;
        }
    },
}
</script> -->