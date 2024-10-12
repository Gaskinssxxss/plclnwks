<template>
    <div class="py-4 px-4 sm:px-8 md:px-10">
        <div class="font-anton uppercase text-2xl sm:text-3xl md:text-4xl flex justify-between">
            <div>
                <h1>Our Manifesto...</h1>
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
        <div v-if="show" class="font-anton uppercase text-base sm:text-xl md:text-2xl pt-4">
            <h1>Main</h1>
            <h1 class="text-xs sm:text-sm md:text-base border-b-2 border-black">
                At NeoBrutal IT Solutions, we embrace the raw and unapologetic beauty of function-first design. In a
                world where form too often overshadows utility, we challenge the status quo by delivering robust,
                no-nonsense digital products that prioritize performance, scalability, and clarity.
            </h1>
            <div class="pt-4">
                <h1>Vision</h1>
                <h1 class="text-xs sm:text-sm md:text-base border-b-2 border-black">We are not here to beautify
                    We are not here to beautify technology with unnecessary
                    ornamentation. We stand
                    for systems that
                    work — bold, powerful, and unembellished. We believe that efficiency, precision, and clarity in code
                    are what drive innovation and progress.</h1>
            </div>
            <div class="pt-4">
                <h1>Core</h1>
                <div
                    class="text-xs sm:text-sm md:text-base flex flex-col lg:flex-row justify-between space-y-4 lg:space-y-0 lg:space-x-10">
                    <h1 class="border-b-2 border-black">Function Over Form: A product should never be weighed down by
                        unnecessary elements. We build
                        with
                        intention, focusing on creating interfaces and systems that get the job done, swiftly and
                        effectively.</h1>
                    <h1 class="border-b-2 border-black">Clarity in Code: Our stack - Vue.js, Node.js, Golang, and Python
                        - reflects our commitment to
                        clean,
                        maintainable, and scalable code. Every line is written with purpose, reducing complexity while
                        enhancing capability.</h1>
                    <h1 class="border-b-2 border-black">Scalability is King: We build for the future. Whether you're
                        deploying an app for hundreds or
                        millions, our solutions will scale with your growth. Golang and Node.js power our backend
                        systems
                        with unmatched speed and efficiency, while Vue.js provides lightweight, dynamic frontend
                        experiences.</h1>
                    <h1 class="border-b-2 border-black">Agile Innovation: NeoBrutalism doesn't mean rigid. We iterate
                        fast, focusing on quick, efficient
                        deployments with robust frameworks like Python for data-driven insights and automation. We
                        thrive on
                        constant evolution, keeping our clients at the cutting edge of what technology can offer.</h1>
                </div>
            </div>
            <div class="pt-4">
                <h1>Commit</h1>
                <h1 class="text-xs sm:text-sm md:text-base border-b-2 border-black">We are the engineers of the
                    unvarnished digital world,
                    dedicated to delivering
                    powerful, streamlined IT solutions that reflect the raw functionality of the neo-brutalist approach.
                    We pledge to create tools that are powerful yet intuitive, unyielding yet adaptive, with technology
                    that speaks for itself.</h1>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            show: true,
            up: false,
            down: true
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
                    Our Manifesto...
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
        <div v-if="show" class="font-anton uppercase text-xl pt-4">
            <h1>Main</h1>
            <h1 class="text-sm border-b-2 border-black">
                At NeoBrutal IT Solutions, we embrace the raw and unapologetic beauty of function-first design. In a
                world where form too often overshadows utility, we challenge the status quo by delivering robust,
                no-nonsense digital products that prioritize performance, scalability, and clarity.
            </h1>
            <div class="pt-4">
                <h1>Vision</h1>
                <h1 class="text-sm border-b-2 border-black">We are not here to beautify technology with unnecessary
                    ornamentation. We stand
                    for systems that
                    work — bold, powerful, and unembellished. We believe that efficiency, precision, and clarity in code
                    are what drive innovation and progress.</h1>
            </div>
            <div class="pt-4">
                <h1>Core</h1>
                <div class="text-sm flex justify-between space-x-10 text-justify">
                    <h1 class="border-b-2 border-black">
                        Function Over Form: A product should never be weighed down by unnecessary elements. We build
                        with
                        intention, focusing on creating interfaces and systems that get the job done, swiftly and
                        effectively.
                    </h1>
                    <h1 class="border-b-2 border-black">
                        Clarity in Code: Our stack - Vue.js, Node.js, Golang, and Python - reflects our commitment to
                        clean,
                        maintainable, and scalable code. Every line is written with purpose, reducing complexity while
                        enhancing capability.
                    </h1>
                    <h1 class="border-b-2 border-black">
                        Scalability is King: We build for the future. Whether you're deploying an app for hundreds or
                        millions, our solutions will scale with your growth. Golang and Node.js power our backend
                        systems
                        with unmatched speed and efficiency, while Vue.js provides lightweight, dynamic frontend
                        experiences.
                    </h1>
                    <h1 class="border-b-2 border-black">
                        Agile Innovation: NeoBrutalism doesn't mean rigid. We iterate fast, focusing on quick, efficient
                        deployments with robust frameworks like Python for data-driven insights and automation. We
                        thrive on
                        constant evolution, keeping our clients at the cutting edge of what technology can offer.
                    </h1>
                </div>
            </div>
            <div class="pt-4">
                <h1>Commit</h1>
                <h1 class="text-sm border-b-2 border-black">We are the engineers of the unvarnished digital world,
                    dedicated to delivering
                    powerful, streamlined IT solutions that reflect the raw functionality of the neo-brutalist approach.
                    We pledge to create tools that are powerful yet intuitive, unyielding yet adaptive, with technology
                    that speaks for itself.</h1>
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