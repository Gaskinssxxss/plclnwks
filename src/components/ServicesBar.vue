<template>
    <div class="py-4 px-4 sm:px-8 md:px-10">
        <div class="font-anton uppercase text-2xl sm:text-3xl md:text-4xl flex justify-between">
            <div>
                <h1>Our Services...</h1>
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
            <div>
                <h1>Big Data</h1>
                <div class="flex flex-col lg:flex-row justify-between space-y-4 lg:space-y-0">
                    <h1 class="text-xs sm:text-sm md:text-base border-b-2 border-black">We In the age of data abundance,
                        we see data not just as information, but as an invaluable resource that requires strategy and
                        deep understanding. Our Big Data services mine, analyze and transform data into insights that
                        deliver strategic value. With the latest technology, we ensure data is not only stored, but also
                        amplified with high-precision analytics that empower your business decisions.</h1>
                </div>
            </div>
            <div class="pt-4">
                <h1>Cloud Backup System</h1>
                <div class="flex flex-col lg:flex-row justify-between space-y-4 lg:space-y-0">
                    <h1 class="text-xs sm:text-sm md:text-base border-b-2 border-black">We In Security starts with
                        preparedness. Our backup services are designed to provide multiple layers of data protection,
                        ready for any risk and disruption. The backup systems we offer operate without compromise,
                        providing peace of mind in the face of potential data loss. Every byte of your data is
                        protected, whenever and wherever it is needed.</h1>
                </div>
            </div>
            <div class="pt-4">
                <h1>Cloud Archiving System</h1>
                <div class="flex flex-col lg:flex-row justify-between space-y-4 lg:space-y-0">
                    <h1 class="text-xs sm:text-sm md:text-base border-b-2 border-black">We In Archiving is more than
                        just storage-it's how we preserve digital history and ensure information continuity. Our
                        Archiving System services offer long-term solutions that are secure, efficient and transparent.
                        With cutting-edge technology, we ensure every valuable document and data remains available and
                        easily accessible without being eroded by time.</h1>
                </div>
            </div>
            <div class="pt-4">
                <h1>Cyber Security as a Service</h1>
                <div class="flex flex-col lg:flex-row justify-between space-y-4 lg:space-y-0">
                    <h1 class="text-xs sm:text-sm md:text-base border-b-2 border-black">We In Amidst ever-evolving cyber
                        threats, security is a non-negotiable imperative. Our Cyber Security service protects your
                        systems and data with a dynamic and layered approach, encompassing end-to-end protection. We
                        safeguard your digital integrity through active monitoring, real-time threat detection and
                        proactive protection, ensuring every access is protected and every threat is decisively
                        addressed.</h1>
                </div>
            </div>
            <div class="pt-4">
                <h1>Web Development</h1>
                <div class="flex flex-col lg:flex-row justify-between space-y-4 lg:space-y-0">
                    <h1 class="text-xs sm:text-sm md:text-base border-b-2 border-black">We build websites with a focus
                        on
                        performance, reliability, and function without unnecessary
                        distractions. Every web project we develop embodies the power of the technology working behind
                        the
                        scenes, with Vue.js and Node.js serving as the solid backbone. There's no excessive
                        ornamentation,
                        just
                        efficiency and clarity guiding users swiftly to their goals. Our websites aren't just aesthetic;
                        they
                        are brutally functional systems, offering scalability that grows with your business.</h1>
                </div>
            </div>
            <div class="pt-4">
                <h1>Mobile Development</h1>
                <h1 class="text-xs sm:text-sm md:text-base border-b-2 border-black">Our mobile applications are designed
                    with the same
                    philosophy: function and speed. Behind the simple interface lies a robust and dependable structure.
                    Dart power the backend to deliver data quickly, while a straightforward
                    front-end
                    design focuses on effective user experience. We don't follow trends of busy, meaningless visuals—our
                    apps are fast-moving, intuitive, and results-driven.</h1>
            </div>
            <div class="pt-4">
                <h1>Sys Analyst</h1>
                <h1 class="text-xs sm:text-sm md:text-base border-b-2 border-black">There is no compromise on quality or
                    scalability. We provide hands-on and focused analysis, ensuring every component operates optimally
                    and integrates seamlessly. Like our manifesto, each component is built with clarity and strength,
                    without unnecessary embellishments. Our sys analysts can develop workflows that are based directly
                    on your company's philosophy and functionality.</h1>
            </div>
            <div class="pt-4">
                <h1>Data Analyst</h1>
                <h1 class="text-xs sm:text-sm md:text-base border-b-2 border-black">We handle data with a raw and honest
                    approach. Using the
                    power of Python, we craft tactical analytic solutions that turn data into actionable insights.
                    Instead of getting lost in overdone visualizations, we focus on the core data that truly matters.
                    Our team builds systems that are brutal in precision, ensuring your data is processed and analyzed
                    accurately to drive fast business decisions.</h1>
            </div>
            <div class="pt-4">
                <h1>Internet of Things (IoT)</h1>
                <h1 class="text-xs sm:text-sm md:text-base border-b-2 border-black">In the world of IoT, we create
                    connectivity that is
                    functional, robust, and efficient. Every device we integrate is connected to an infrastructure built
                    without frills, maximizing functionality and power. We deliver IoT technology that works seamlessly
                    behind the scenes, offering strong control and automation without needing to be flashy. From devices
                    to data, each component operates with brutal precision and strength that directly serves your
                    business needs.</h1>
            </div>
            <div class="pt-4">
                <h1>Robotics</h1>
                <h1 class="text-xs sm:text-sm md:text-base border-b-2 border-black">A robot lives according to its task,
                    with programs and functionality embedded in it. With our skills we can create robots that can help
                    you in all your problem needs.</h1>
            </div>
            <div class="pt-4">
                <h1>3d Modeling</h1>
                <h1 class="text-xs sm:text-sm md:text-base border-b-2 border-black">The need for 3d models is
                    increasing, adding to the strength of products that involve 3d modeling. With visual impact being
                    the benchmark of a product's beauty, injecting elements of 3d modeling into your product greetings
                    will greatly affect your business prospects.</h1>
            </div>
            <div class="pt-4">
                <h1>Election Survey & Tim management</h1>
                <h1 class="text-xs sm:text-sm md:text-base border-b-2 border-black">Today's political developments
                    require political actors to do innovative work to achieve success. The role of survey institutions
                    and management teams is very influential in assisting political actors in carrying out their
                    political work.</h1>
            </div>
            <div class="pt-4 sm:pt-10 text-sm sm:text-lg border-b-2 border-gray-300 pb-4 sm:pb-2">
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
    <div class="py-4 px-10">
        <div class="font-anton uppercase text-4xl flex justify-between">
            <div>
                <h1>
                    Our Services...
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
            <h1>Web Development</h1>
            <div class="flex justify-between space-x-4">
                <h1 class="text-sm border-b-2 border-black">
                    We build websites with a focus on performance, reliability, and function without unnecessary
                    distractions. Every web project we develop embodies the power of the technology working behind the
                    scenes, with Vue.js and Node.js serving as the solid backbone. There's no excessive ornamentation,
                    just
                    efficiency and clarity guiding users swiftly to their goals. Our websites aren't just aesthetic;
                    they
                    are brutally functional systems, offering scalability that grows with your business.
                </h1>
            </div>
            <div class="pt-4">
                <h1>Mobile Development</h1>
                <h1 class="text-sm border-b-2 border-black">Our mobile applications are designed with the same
                    philosophy: function and speed. Behind the simple interface lies a robust and dependable structure.
                    Dart power the backend to deliver data quickly, while a straightforward
                    front-end
                    design focuses on effective user experience. We don't follow trends of busy, meaningless visuals—our
                    apps are fast-moving, intuitive, and results-driven.</h1>

            </div>
            <div class="pt-4">
                <h1>Sys Analyst</h1>
                <h1 class="text-sm border-b-2 border-black">When developing complex systems, we remove confusion with
                    bold and straightforward solutions. The systems we design are based on transparent architecture,
                    allowing businesses to move without obstacles. There's no compromise on quality or scalability. We
                    provide direct, focused analysis, ensuring every system component operates optimally and integrates
                    seamlessly. Like our manifesto, every component is built with clarity and strength, without
                    unnecessary embellishments.</h1>
            </div>
            <div class="pt-4">
                <h1>Data Analyst</h1>
                <h1 class="text-sm border-b-2 border-black">We handle data with a raw and honest approach. Using the
                    power of Python, we craft tactical analytic solutions that turn data into actionable insights.
                    Instead of getting lost in overdone visualizations, we focus on the core data that truly matters.
                    Our team builds systems that are brutal in precision, ensuring your data is processed and analyzed
                    accurately to drive fast business decisions.</h1>
            </div>
            <div class="pt-4">
                <h1>Internet of Things (IoT)</h1>
                <h1 class="text-sm border-b-2 border-black">In the world of IoT, we create connectivity that is
                    functional, robust, and efficient. Every device we integrate is connected to an infrastructure built
                    without frills, maximizing functionality and power. We deliver IoT technology that works seamlessly
                    behind the scenes, offering strong control and automation without needing to be flashy. From devices
                    to data, each component operates with brutal precision and strength that directly serves your
                    business needs.</h1>
            </div>
            <div class="flex justify-end pt-10">
                <h1>Click The Button <span class="px-4">
                        <button class="bg-black rounded-lg" @click="scrollToEmergency">
                            <div
                                class="text-start transition-transform duration-300 ease-linear transform -translate-x-1 -translate-y-1 hover:-translate-x-0 hover:-translate-y-0 bg-che rounded-lg border-2 border-black p-2">
                                <h1>
                                    Emergency Call
                                </h1>
                            </div>
                        </button>
                    </span>, if ur in emergency sistuation.</h1>
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
        },
        scrollToEmergency() {
            const emergencySection = document.getElementById("emergency-section");
            if (emergencySection) {
                emergencySection.scrollIntoView({ behavior: "smooth" });
            }
        }
    },
}
</script> -->