<template>
    <div>
        <div class="border-b-2 border-black">
            <div class="px-4 pt-4 pb-4 md:pb-8">
                <NavBar />
            </div>
        </div>
        <div class="border-b-2 border-black pb-10">
            <div class="pt-4 sm:pt-10 px-3 sm:px-10 lg:px-12">
                <HeaderBar />
            </div>
        </div>
        <div class="border-b-2 border-black px-3 sm:px-5 py-2 lg:px-10">
            <ManifestoBar />
        </div>
        <div class="border-b-2 border-black px-3 sm:px-5 py-2 lg:px-10">
            <WebDev />
        </div>
        <div class="border-b-2 border-black px-3 sm:px-5 py-2 lg:px-10">
            <IntrictBar />
        </div>
        <div class="border-b-2 border-black px-3 sm:px-5 py-2 lg:px-10">
            <ServicesBar />
        </div>
        <div class="border-b-2 border-black px-3 sm:px-5 py-2 lg:px-10">
            <ourClient />
        </div>
        <div class="border-b-2 border-black px-3 sm:px-5 py-2 lg:px-10">
            <EmailCall />
        </div>
        <div class="border-b-2 border-black px-3 sm:px-5 py-2 lg:px-10">
            <FooterBar />
        </div>
    </div>
</template>

<script>
import NavBar from "../components/NavBar.vue"
import HeaderBar from "../components/HeaderBar.vue"
import ManifestoBar from "../components/ManifestoBar.vue"
import WebDev from "../components/WebDev.vue"
import IntrictBar from "../components/IntrictBar.vue"
import ServicesBar from "../components/ServicesBar.vue"
import ourClient from "../components/OurClient.vue"
import EmailCall from "../components/EmailCall.vue"
import FooterBar from "../components/FooterBar"

export default {
    components: {
        NavBar,
        HeaderBar,
        ManifestoBar,
        WebDev,
        IntrictBar,
        ServicesBar,
        ourClient,
        EmailCall,
        FooterBar
    },
    mounted() {
        this.scrollToTop()
    },
    methods: {
        scrollToTop() {
            window.scrollTo({
                top: 0,
                behavior: "smooth"
            });
        },
    },
}
</script>


<!-- <template>
    <div>
        <div class="border-b-2 border-black">
            <div class="px-4 pt-4 pb-8">
                <NavBar />
            </div>
        </div>
        <div class="border-b-2 border-black pb-20">
            <div class="pt-10 px-10">
                <HeaderBar />
            </div>
        </div>
        <div class="border-b-2 border-black px-5 py-2">
            <ManifestoBar />
        </div>
        <div class="border-b-2 border-black px-5 py-2">
            <WebDev />
        </div>
        <div class="border-b-2 border-black px-5 py-2">
            <IntrictBar />
        </div>
        <div class="border-b-2 border-black px-5 py-2">
            <ServicesBar />
        </div>
        <div class="border-b-2 border-black px-5 py-2">
            <ourClient />
        </div>
        <div class="border-b-2 border-black px-5 py-2">
            <EmailCall />
        </div>
        <div class="border-b-2 border-black px-5 py-2">
            <FooterBar />
        </div>
    </div>
</template>

<script>
import NavBar from "../components/NavBar.vue"
import HeaderBar from "../components/HeaderBar.vue"
import ManifestoBar from "../components/ManifestoBar.vue"
import WebDev from "../components/WebDev.vue"
import IntrictBar from "../components/IntrictBar.vue"
import ServicesBar from "../components/ServicesBar.vue"
import ourClient from "../components/OurClient.vue"
import EmailCall from "../components/EmailCall.vue"
import FooterBar from "../components/FooterBar"

export default {
    components: {
        NavBar,
        HeaderBar,
        ManifestoBar,
        WebDev,
        IntrictBar,
        ServicesBar,
        ourClient,
        EmailCall,
        FooterBar
    }
}
</script> -->