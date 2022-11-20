<script setup>
import "vue3-carousel/dist/carousel.css";
import { Carousel, Slide } from "vue3-carousel";

const slides = [
  {
    id: "1",
    image: "mickey1.jpg",
  },
  {
    id: "2",
    image: "mickey2.jpg",
  },
  {
    id: "3",
    image: "mickey3.jpg",
  },
  {
    id: "4",
    image: "mickey4.jpg",
  },
];
</script>

<template>
  <div class="home">
    <HeaderToko />
    <!-- Breadcrumb Section Begin -->
    <div class="breacrumb-section">
      <div class="container">
        <div class="row">
          <div class="col-lg-12">
            <div class="breadcrumb-text product-more text-left">
              <router-link to="/"
                ><a href="./home.html"
                  ><i class="fa fa-home"></i> Home</a
                ></router-link
              >
              <span>Detail</span>
            </div>
          </div>
        </div>
      </div>
    </div>
    <!-- Breadcrumb Section Begin -->

    <!-- Product Shop Section Begin -->
    <section class="product-shop spad page-details">
      <div class="container">
        <div class="row">
          <div class="col-lg-12">
            <div class="row">
              <div class="col-lg-6">
                <div class="product-pic-zoom">
                  <img class="product-big-img" :src="gambar" alt="" />
                </div>
                <Carousel items-to-show="3" :wrap-around="true" autoplay="2000">
                  <Slide v-for="slide in slides" :key="slide">
                    <div class="product-thumbs">
                      <div class="product-thumbs-track ps-slider">
                        <div class="pt">
                          <img v-bind:src="'/img/' + slide.image" alt="" />
                        </div>
                      </div>
                    </div>
                  </Slide>
                  <template #addons>
                    <Navigation />
                    <Pagination />
                  </template>
                </Carousel>
              </div>
              <div class="col-lg-6">
                <div class="product-details">
                  <div class="pd-title text-left">
                    <span>oranges</span>
                    <h3>Pure Pineapple</h3>
                  </div>
                  <div class="pd-desc text-left">
                    <p>
                      Lorem ipsum dolor sit amet consectetur adipisicing elit.
                      Corporis, error officia. Rem aperiam laborum voluptatum
                      vel, pariatur modi hic provident eum iure natus quos non a
                      sequi, id accusantium! Autem.
                    </p>
                    <p>
                      Lorem ipsum dolor sit, amet consectetur adipisicing elit.
                      Quam possimus quisquam animi, commodi, nihil voluptate
                      nostrum neque architecto illo officiis doloremque et
                      corrupti cupiditate voluptatibus error illum. Commodi
                      expedita animi nulla aspernatur. Id asperiores blanditiis,
                      omnis repudiandae iste inventore cum, quam sint molestiae
                      accusamus voluptates ex tempora illum sit perspiciatis.
                      Nostrum dolor tenetur amet, illo natus magni veniam quia
                      sit nihil dolores. Commodi ratione distinctio harum
                      voluptatum velit facilis voluptas animi non laudantium, id
                      dolorem atque perferendis enim ducimus? A exercitationem
                      recusandae aliquam quod. Itaque inventore obcaecati, unde
                      quam impedit praesentium veritatis quis beatae ea atque
                      perferendis voluptates velit architecto?
                    </p>
                    <h4>$495.00</h4>
                  </div>
                  <div class="quantity">
                    <router-link to="/cart">
                      <a href="shopping-cart.html" class="primary-btn pd-cart"
                        >Add To Cart</a
                      ></router-link
                    >
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <!-- Product Shop Section End -->
    <RelatedProduct />
    <FooterSection />
  </div>
</template>

<script>
import HeaderToko from "@/components/HeaderToko.vue";
import FooterSection from "@/components/FooterSection.vue";
import RelatedProduct from "@/components/RelatedProduct.vue";

export default {
  name: "homeView",
  components: {
    HeaderToko,
    FooterSection,
    Carousel,
    Slide,
    RelatedProduct,
  },
  data() {
    return {
      gambar: "img/mickey1.jpg",
      thumb: [
        "img/mickey1.jpg",
        "img/mickey2.jpg",
        "img/mickey3.jpg",
        "img/mickey4.jpg",
      ],
    };
  },
  methods: {
    changeImage(urlImage) {
      this.gambar = urlImage;
    },
  },
};
</script>

<style scoped>
.pt {
  margin-left: 5px;
  margin-right: 5px;
}
</style>
