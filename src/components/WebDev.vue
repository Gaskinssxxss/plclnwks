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
                <div>
                    <h1>Ideation and Needs Identification</h1>
                    <h1 class="text-xs sm:text-sm md:text-base border-b-2 border-black">
                        Ideation and Needs Identification
                        Determine user and industry needs with a keen vision. Why just follow trends, when innovation
                        can be created from real needs? Why not challenge the status quo with a product that focuses on
                        safety, reliability and design rigor?
                    </h1>
                </div>
                <div>
                    <h1>Neobrutalist Product Design</h1>
                    <h1 class="text-xs sm:text-sm md:text-base border-b-2 border-black">Avoiding wasteful aesthetics.
                        Why are elements without purpose present? Function, not
                        decoration, is the soul of every component. Transparency in UI and UX, creating an honest and
                        authentic experience for users at every step.</h1>
                </div>
                <div>
                    <h1>Architecture and Security Determination</h1>
                    <h1 class="text-xs sm:text-sm md:text-base border-b-2 border-black">
                        Choosing resilience as the foundation. Only solutions that guarantee data security in all
                        circumstances deserve to be here. Why stop at the usual standards when backup, archiving, and
                        cybersecurity systems can protect like no other?
                    </h1>
                </div>
                <div>
                    <h1>Resilient Backend Development</h1>
                    <h1 class="text-xs sm:text-sm md:text-base border-b-2 border-black">
                        A backend architecture, resilient and reliable, that is not only ready to grow, but also ready
                        to fight back. Redundancy and fail-safe-why allow data risk, when resilience can be
                        strengthened? Unbreakable user authentication, every loophole a challenge to overcome.
                    </h1>
                </div>
                <div>
                    <h1>Implementation of Key Features with Maximum Efficiency</h1>
                    <h1 class="text-xs sm:text-sm md:text-base border-b-2 border-black">
                        Only the core features stand out-big data, backup, archiving, and cybersecurity. Why overload
                        the product with features that don't support the main purpose? Each element focuses on
                        effectiveness and purpose, without distraction.
                    </h1>
                </div>
                <div>
                    <h1>Side Services Integration</h1>
                    <h1 class="text-xs sm:text-sm md:text-base border-b-2 border-black">
                        Side services that exist only to support the big mission, nothing more. Why mix goals if the
                        core product is clarity? Additional services like Web Development or IoT are there to
                        strengthen, not obscure.
                    </h1>
                </div>
                <div>
                    <h1>Rigorous Testing and Iterations</h1>
                    <h1 class="text-xs sm:text-sm md:text-base border-b-2 border-black">
                        Durability and safety are tested with uncompromising intensity. Tests that don't just qualify,
                        but challenge the toughness of the product. Why compromise on safety when durability can be
                        proven under every condition?
                    </h1>
                </div>
                <div>
                    <h1>User-Driven Enhancements</h1>
                    <h1 class="text-xs sm:text-sm md:text-base border-b-2 border-black">
                        Developments that are based on true user needs, not trends. The product evolves to strengthen,
                        not to add burden. Why sacrifice design and function for a temporary trend?
                    </h1>
                </div>
                <div>
                    <h1>Active Security Deployment and Monitoring</h1>
                    <h1 class="text-xs sm:text-sm md:text-base border-b-2 border-black">
                        Security that is constantly monitored, threats that are caught in seconds. Why allow for risk
                        when every potential hazard can be identified and dealt with swiftly?
                    </h1>
                </div>
                <div>
                    <h1>Periodic Maintenance and Upgrades</h1>
                    <h1 class="text-xs sm:text-sm md:text-base border-b-2 border-black">
                        Consistency in safety and reliability, strictly maintained. Why forgo long-term protection when
                        every product can be continuously maintained and strengthened for the future?
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