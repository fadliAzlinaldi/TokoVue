<script setup>
import "vue3-carousel/dist/carousel.css";
import { Carousel, Slide } from "vue3-carousel";

const slides = [
  {
    id: "1",
    image: "logo-1.png",
  },
  {
    id: "2",
    image: "logo-2.png",
  },
  {
    id: "3",
    image: "logo-3.png",
  },
  {
    id: "4",
    image: "logo-4.png",
  },
  {
    id: "5",
    image: "logo-5.png",
  },
];
</script>

<template>
  <div class="partner-wrapper">
    <!-- Partner Section Begin -->
    <Carousel items-to-show="5" :wrap-around="true" autoplay="2000">
      <Slide v-for="slide in slides" :key="slide">
        <div class="partner-logo">
          <div class="container">
            <div class="logo-carousel">
              <div class="logo-item">
                <div class="tablecell-inner">
                  <img
                    v-bind:src="'/img/logo-carousel/' + slide.image"
                    alt=""
                  />
                </div>
              </div>
            </div>
          </div>
        </div>
      </Slide>
      <template #addons>
        <Navigation />
        <Pagination />
      </template>
    </Carousel>
    <!-- Partner Section End -->
  </div>
</template>

<script>
export default {
  name: "PartnerSection",
  components: {
    Carousel,
    Slide,
  },
};
</script>

<style>
.partner-wrapper {
  background: #303030;
  height: 130px;
}
</style>
