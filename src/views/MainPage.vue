<template>
  <div class="font-anton">
    <div>
      <Navi />
    </div>
    <div class="pb-16" id="about">
      <Banner />
    </div>
    <div id="visi">
      <BannerTwo />
    </div>
    <div id="services">
      <BannerThree />
    </div>
    <div class="pb-4" id="clients">
      <ServicesPart />
    </div>
    <div id="footer">
      <OurClient />
    </div>
    <div class="pb-4">
      <EmailCall />
    </div>
    <div class="pt-10 border-t-2 border-black">
      <FooterBar />
    </div>
  </div>
</template>

<script>
import Banner from "@/components/BannerPart.vue";
import BannerThree from "@/components/BannerThreePart.vue";
import BannerTwo from "@/components/BannerTwoPart.vue";
import Navi from "@/components/NavigationPart.vue";
import OurClient from "@/components/OurClientn.vue";
import ServicesPart from "@/components/ServicesPart.vue";
import FooterBar from "@/components/FooterBar.vue";
import EmailCall from "@/components/EmailCall.vue";

export default {
  components: {
    Navi,
    Banner,
    BannerTwo,
    BannerThree,
    OurClient,
    ServicesPart,
    EmailCall,
    FooterBar,
  },
};
</script>
