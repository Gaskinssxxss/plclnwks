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
                <!-- At NeoBrutal IT Solutions, we embrace the raw and unapologetic beauty of function-first design. In a
                world where form too often overshadows utility, we challenge the status quo by delivering robust,
                no-nonsense digital products that prioritize performance, scalability, and clarity. -->
                We move against the tide of complexity and obscurity. Rooted in digital honesty and decisiveness of
                form, we exist to simplify the complex, protect the vulnerable and archive the valuable. Our technology
                is not just a tool, but a pillar that supports a safe and empowered data ecosystem. In the form of
                neobrutalism, we defy superficial aesthetics and focus on the essence: function above all, protection
                without compromise.
                Big data is the raw resource, backup systems are the shield, archiving is the foundation, and cyber
                security is the fortress. We don't just build technology; we build resistance, against insecurity, data
                chaos, and the antithesis of neobrutalism that undermines transparency.
            </h1>
            <div class="pt-4">
                <h1>Vision</h1>
                <h1 class="text-xs sm:text-sm md:text-base border-b-2 border-black">
                    <!-- We are not here to beautify
                    We are not here to beautify technology with unnecessary
                    ornamentation. We stand
                    for systems that
                    work — bold, powerful, and unembellished. We believe that efficiency, precision, and clarity in code
                    are what drive innovation and progress. -->
                    To be the guardian of digital honesty and the pioneer of resilient data architecture, where every
                    byte is protected and every piece of information has its rightful place.
                </h1>
            </div>
            <div class="pt-4">
                <h1>Core</h1>
                <div
                    class="text-xs sm:text-sm md:text-base flex flex-col lg:flex-row justify-between space-y-4 lg:space-y-0 lg:space-x-10">
                    <h1 class="border-b-2 border-black">
                        <!-- Function Over Form: A product should never be weighed down by
                        unnecessary elements. We build
                        with
                        intention, focusing on creating interfaces and systems that get the job done, swiftly and
                        effectively. -->
                        Integrity Without Bargaining
                        We won't bow to compromise, won't fall for the temptation of shiny but hollow data. Our
                        infrastructure is built on truth, security, and steadfastness. We reject the deceit that
                        paralyzes trust; we are an unshakable fortress, standing firm against digital dishonesty.
                    </h1>
                    <h1 class="border-b-2 border-black">
                        <!-- Clarity in Code: Our stack - Vue.js, Node.js, Golang, and Python
                        - reflects our commitment to
                        clean,
                        maintainable, and scalable code. Every line is written with purpose, reducing complexity while
                        enhancing capability. -->
                        Protection as the Foundation
                        In every line of code and every design, our goal is only one: protect relentlessly. Our backup
                        system is our shield, our cybersecurity is our night watchman, neither of which will leave
                        anything precious at risk. Resilience is our mantra, protection is the spirit that drives every
                        product we make.
                    </h1>
                    <h1 class="border-b-2 border-black">
                        <!-- Scalability is King: We build for the future. Whether you're
                        deploying an app for hundreds or
                        millions, our solutions will scale with your growth. Golang and Node.js power our backend
                        systems
                        with unmatched speed and efficiency, while Vue.js provides lightweight, dynamic frontend
                        experiences. -->
                        Neobrutalist Design Assertiveness
                        We are against all gimmicks, rejecting deceptive aesthetics. Our designs are a reflection of
                        sincerity and boldness. These are not solutions shrouded in lies; they are open and bold
                        honesty. Each of our products is a resistance to pointless complexity, presenting strength and
                        honesty in its purest form.
                    </h1>
                    <h1 class="border-b-2 border-black">
                        <!-- Agile Innovation: NeoBrutalism doesn't mean rigid. We iterate
                        fast, focusing on quick, efficient
                        deployments with robust frameworks like Python for data-driven insights and automation. We
                        thrive on
                        constant evolution, keeping our clients at the cutting edge of what technology can offer. -->
                        Archiving for the Future
                        We don't just store; we preserve the flame of the past for future generations. Every piece of
                        data is a legacy worth fighting for, a priceless trace of history. We challenge digital
                        negligence and vow to immortalize the precious, making it a pillar for a wiser and safer future.
                    </h1>
                </div>
            </div>
            <div class="pt-4">
                <h1>Commit</h1>
                <h1 class="text-xs sm:text-sm md:text-base border-b-2 border-black">
                    <!-- We are the engineers of the
                    unvarnished digital world,
                    dedicated to delivering
                    powerful, streamlined IT solutions that reflect the raw functionality of the neo-brutalist approach.
                    We pledge to create tools that are powerful yet intuitive, unyielding yet adaptive, with technology
                    that speaks for itself. -->
                    We are committed to maintaining the integrity of our products by bringing big data technology,
                    backup, and security as the main services that protect your every digital corner. Side services such
                    as web development, data analytics, IoT, and social surveys only support our main mission, without
                    compromising our core focus. It's a promise to always be at the forefront of digital defense,
                    protecting the vulnerable and simplifying the complex.
                </h1>
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