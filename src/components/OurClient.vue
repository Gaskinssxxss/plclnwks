<template>
    <div class="py-4 px-4 sm:px-8 md:px-10">
        <div class="font-anton uppercase text-2xl sm:text-3xl md:text-4xl flex justify-between">
            <div>
                <h1>Our Clients...</h1>
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
            <div class="space-y-4 sm:space-y-8 2xl:space-y-4 pt-4 grid grid-cols-1 sm:grid-cols-3">
                <div class="flex items-center space-x-2 border-b-2 border-black">
                    <img class="max-w-16 max-h-16 lg:max-w-20 lg:max-h-20 grayscale" src="../assets/bombs-2.png" alt="">
                    <div>
                        <h1>Political Volunteer System</h1>
                    </div>
                </div>
                <div class="flex items-center space-x-2 border-b-2 border-black">
                    <img class="max-w-16 max-h-16 lg:max-w-20 lg:max-h-20 grayscale" src="../assets/nusa.png" alt="">
                    <div>
                        <h1>Online Travel Agent Booking System</h1>
                    </div>
                </div>
                <div class="flex items-center space-x-2 border-b-2 border-black pb-4 sm:pb-0">
                    <img class="max-w-16 max-h-16 lg:max-w-20 lg:max-h-20 grayscale" src="../assets/dnk.png" alt="">
                    <div>
                        <h1>News Portal System</h1>
                    </div>
                </div>
                <div class="flex items-center space-x-2 border-b-2 border-black pb-4 sm:pb-0">
                    <img class="max-w-16 max-h-16 lg:max-w-20 lg:max-h-20 grayscale" src="../assets/bimakita.png"
                        alt="">
                    <div>
                        <h1>News Portal System</h1>
                    </div>
                </div>
                <div class="flex items-center space-x-2 border-b-2 border-black">
                    <img class="max-w-16 max-h-16 lg:max-w-20 lg:max-h-20 grayscale" src="../assets/lpkni.png" alt="">
                    <div>
                        <h1>Lembaga Perlindungan Konsumen nasional indonesia</h1>
                    </div>
                </div>
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
                    Our Clients...
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
            <div class="space-y-4 pt-4 flex justify-between">
                <div class="flex justify-start items-center space-x-2 border-b-2 border-black">
                    <img class="max-w-20 max-h-20 grayscale" src="../assets/bombs-2.png" alt="">
                    <div>
                        <h1>Political Volunteer System</h1>
                    </div>
                </div>
                <div class="flex justify-start items-center space-x-2 border-b-2 border-black">
                    <img class="max-w-20 max-h-20 grayscale" src="../assets/nusa.png" alt="">
                    <div>
                        <h1>Online Travel Agent Booking System</h1>
                    </div>
                </div>
                <div class="flex justify-start items-center space-x-2 border-b-2 border-black">
                    <img class="max-w-20 max-h-20 grayscale" src="../assets/dnk.png" alt="">
                    <div>
                        <h1>News Portal System</h1>
                    </div>
                </div>
                <div class="flex justify-start items-center space-x-2 border-b-2 border-black">
                    <img class="max-w-20 max-h-20 grayscale" src="../assets/bimakita.png" alt="">
                    <div>
                        <h1>News Portal System</h1>
                    </div>
                </div>
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