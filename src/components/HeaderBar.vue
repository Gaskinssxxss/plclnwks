<template>
    <div class="font-anton uppercase">
        <div class="flex flex-col 2xl:flex-row justify-between">
            <div class="text-5xl sm:text-6xl md:text-7xl lg:text-9xl pt-4 sm:pt-0">
                <div class="bg-black p-2">
                    <h1 class="text-che">pollacheial</h1>
                </div>
                <h1>networks</h1>
                <h1>tech</h1>
                <div class="pt-4 sm:pt-10 text-sm sm:text-lg border-b-2 border-gray-300 pb-10 sm:pb-2">
                    <h1>Click The Button <span class="px-1 sm:px-4">
                            <button class="bg-black rounded-lg text-xl md:text-4xl" @click="scrollToEmergency">
                                <div
                                    class="text-start transition-transform duration-300 ease-linear transform -translate-x-1 -translate-y-1 hover:-translate-x-0 hover:-translate-y-0 bg-che rounded-lg border-2 border-black p-2">
                                    <h1>
                                        Emergency Call
                                    </h1>
                                </div>
                            </button>
                        </span>, if u on emergency situation.</h1>
                </div>
            </div>
            <div class="text-2xl sm:text-3xl md:text-4xl lg:text-5xl pt-2 sm:pt-6 md:pt-4 2xl:pt-0">
                <h1>slow but explosive</h1>
                <h1 class="text-start">theatrical arts of geek's</h1>
                <TopologiAttack />
            </div>
        </div>
    </div>
</template>

<script>
import TopologiAttack from './topologiAttack.vue';

export default {
    components: {
        TopologiAttack
    },
    data() {
        return {
            front: false,
            back: false,
            arc: false
        }
    },
    methods: {
        one() {
            this.front = true;
            this.back = false;
            this.arc = false;
        },
        two() {
            this.front = false;
            this.back = true;
            this.arc = false;
        },
        three() {
            this.front = false;
            this.back = false;
            this.arc = true;
        },
        close() {
            this.front = false;
            this.back = false;
            this.arc = false;
        },
        scrollToEmergency() {
            const emergencySection = document.getElementById("emergency-section");
            if (emergencySection) {
                emergencySection.scrollIntoView({ behavior: "smooth" });
            }
        }
    },
}
</script>


<!-- <template>
    <div class="font-anton uppercase">
        <div class="flex justify-between">
            <div class="text-9xl">
                <div class="bg-black p-2">
                    <h1 class="text-che">pollacheial</h1>
                </div>
                <h1>networks</h1>
                <h1>tech</h1>
            </div>
            <div class="text-5xl">
                <h1>slow but explosive</h1>
                <h1 class="border-b-2 border-gray-300">theatrical arts of geek's</h1>
                <div class="text-2xl pt-4">
                    <div class="flex justify-between bg-black text-gray-300 p-6">
                        <div>
                            <h1>frontend</h1>
                            <div class="text-lg space-y-2 pt-2">
                                <h1 class="border-b-2 border-gray-300">Vue Js</h1>
                                <h1 class="border-b-2 border-gray-300">Alpine Js</h1>
                                <h1 class="border-b-2 border-gray-300">Tailwind Css</h1>
                                <h1 class="border-b-2 border-gray-300">Bootstrap</h1>
                            </div>
                        </div>
                        <div>
                            <h1>Backend</h1>
                            <div class="text-lg space-y-2 pt-2">
                                <h1 class="border-b-2 border-gray-300">Node js</h1>
                                <h1 class="border-b-2 border-gray-300">Golang</h1>
                                <h1 class="border-b-2 border-gray-300">Python</h1>
                                <h1 class="border-b-2 border-gray-300">Dart</h1>
                            </div>
                        </div>
                        <div>
                            <h1>Architecture</h1>
                            <div class="text-lg space-y-2 pt-2">
                                <h1 class="border-b-2 border-gray-300">MicroServices</h1>
                                <h1 class="border-b-2 border-gray-300">Monolith</h1>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="flex justify-end pt-6 text-lg">
                    <h1>Click The Button <span class="px-4">
                            <button class="bg-black rounded-lg" @click="scrollToEmergency">
                                <div
                                    class="text-start transition-transform duration-300 ease-linear transform -translate-x-1 -translate-y-1 hover:-translate-x-0 hover:-translate-y-0 bg-che rounded-lg border-2 border-black p-2">
                                    <h1>
                                        Emergency Call
                                    </h1>
                                </div>
                            </button>
                        </span>, if u on emergency sistuation.</h1>
                </div>
            </div>
        </div>
    </div>
</template> -->