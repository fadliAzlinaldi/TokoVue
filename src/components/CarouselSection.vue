<script setup>
import "vue3-carousel/dist/carousel.css";
import { Carousel, Slide, Pagination, Navigation } from "vue3-carousel";

const slides = [
  {
    id: "1",
    image: "mickey1.jpg",
    catagoryName: "Coat",
    productName: "Mickey Baggy",
    productPrice: 14.0,
  },
  {
    id: "2",
    image: "women-2.jpg",
    catagoryName: "Shoes",
    productName: "Guangzhou sweater",
    productPrice: 13.0,
  },
  {
    id: "3",
    image: "women-3.jpg",
    catagoryName: "Towel",
    productName: "Pure Pineapple",
    productPrice: 34.0,
  },
];
</script>

<template>
  <div>
    <!-- Women Banner Section Begin -->
    <Carousel items-to-show="3" :wrap-around="true">
      <Slide v-for="slide in slides" :key="slide">
        <div class="product-item">
          <div class="pi-pic">
            <img v-bind:src="'/img/products/' + slide.image" />
            <ul>
              <li class="w-icon active">
                <a href="#"><i class="icon_bag_alt"></i></a>
              </li>
              <li class="quick-view">
                <router-link to="/product">+ Quick View</router-link>
              </li>
            </ul>
          </div>
          <div class="pi-text">
            <div class="catagory-name">{{ slide.catagoryName }}</div>
            <a href="#">
              <h5 class="product-name">{{ slide.productName }}</h5>
            </a>
            <div class="product-price">
              $
              {{ slide.productPrice }}
            </div>
          </div>
        </div>
      </Slide>
      <template #addons>
        <Navigation />
        <Pagination />
      </template>
    </Carousel>
    <!-- Women Banner Section End -->
  </div>
</template>

<script>
export default {
  name: "CarouselSection",
  components: {
    Carousel,
    Slide,
    Pagination,
    Navigation,
  },
};
</script>

<style scoped>
.product-item {
  margin-top: 100px;
}
.product-item img {
  max-height: 300px;
  min-width: 245px;
}
</style>
