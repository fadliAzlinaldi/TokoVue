<script setup>
import "vue3-carousel/dist/carousel.css";
import { Carousel, Slide, Pagination, Navigation } from "vue3-carousel";

const slides = [
  {
    id: "1",
    image: "hero-1.jpg",
  },
  {
    id: "2",
    image: "hero-2.jpg",
  },
  {
    id: "3",
    image: "hero-3.jpg",
  },
];
</script>

<template>
  <div>
    <!-- Hero Section Begin -->
    <Carousel>
      <Slide v-for="slide in slides" :key="slide">
        <div class="carousel__item">
          <div
            class="single-hero-items set-bg"
            v-bind:style="{ backgroundImage: 'url(img/' + slide.image + ')' }"
          >
            <div class="container">
              <div class="row">
                <div class="banner-info">
                  <div class="col-lg-5">
                    <span>Bag,kids</span>
                    <h1>Black friday</h1>
                    <p class="desc">
                      Lorem ipsum dolor sit amet, consectetur adipisicing elit,
                      sed do eiusmod tempor incididunt ut labore et dolore
                    </p>
                    <a href="#" class="primary-btn">Shop Now</a>
                  </div>
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
    <!-- Hero Section End -->
  </div>
</template>

<script>
export default {
  name: "HeroSection",
  components: {
    Carousel,
    Slide,
    Pagination,
    Navigation,
  },
};
</script>

<style scoped>
.set-bg {
  width: 100%;
  height: 500px;
}
.banner-info {
  margin-top: 100px;
  margin-left: 100px;
  text-align: left;
}
</style>
