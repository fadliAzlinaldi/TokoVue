<template>
  <div class="home">
    <HeaderToko />
    <HeroSection />
    <CarouselSection />
    <GallerySection />
    <PartnerSection />
    <FooterSection />
  </div>
</template>

<script>
import HeaderToko from "@/components/HeaderToko.vue";
import HeroSection from "@/components/HeroSection.vue";
import CarouselSection from "@/components/CarouselSection.vue";
import GallerySection from "@/components/GallerySection.vue";
import PartnerSection from "@/components/PartnerSection.vue";
import FooterSection from "@/components/FooterSection.vue";

export default {
  name: "homeView",
  components: {
    HeaderToko,
    HeroSection,
    CarouselSection,
    GallerySection,
    PartnerSection,
    FooterSection,
  },
};
</script>
