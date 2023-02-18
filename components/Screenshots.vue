<template>
  <section class="pt-30 pb-30" id="app" style="padding-top: 0">
    <div class="container-fluid">
      <div class="row justify-content-center">
        <div class="col-md-12 col-lg-12 col-xl-12">
          <div class="w-100">
            <img width="100%" src="../static/assets/img/2LTS_5.png" alt="" />
          </div>
        </div>
      </div>
      <div class="app-shot-one__carousel thm__owl-carousel d-none">
        <swiper :options="swiperOptions">
          <swiper-slide>
            <!-- slingle app image -->
            <div class="item">
              <img src="/assets/img/feature/app-img.png" alt="" />
            </div>
            <!-- slingle app image -->
          </swiper-slide>

          <swiper-slide>
            <!-- slingle app image -->
            <div class="item">
              <img src="/assets/img/feature/app-img2.png" alt="" />
            </div>
            <!-- slingle app image -->
          </swiper-slide>

          <swiper-slide>
            <!-- slingle app image -->
            <div class="item">
              <img src="/assets/img/feature/app-img3.png" alt="" />
            </div>
            <!-- slingle app image -->
          </swiper-slide>

          <swiper-slide>
            <!-- slingle app image -->
            <div class="item">
              <img src="/assets/img/feature/app-img4.png" alt="" />
            </div>
            <!-- slingle app image -->
          </swiper-slide>

          <swiper-slide>
            <!-- slingle app image -->
            <div class="item">
              <img src="/assets/img/feature/app-img5.png" alt="" />
            </div>
            <!-- slingle app image -->
          </swiper-slide>
        </swiper>
        <div class="swiper-pagination owl-dots" slot="pagination"></div>
      </div>
      <!-- /.app-shot-one__carousel owl-theme owl-carousel -->
    </div>
    <!-- /.container-fluid -->
  </section>
</template>

<script>
import { Swiper, SwiperSlide, directive } from "vue-awesome-swiper";
import "swiper/css/swiper.css";
export default {
  name: "Screenshots",
  components: {
    Swiper,
    SwiperSlide,
  },
  directives: {
    swiper: directive,
  },
  data() {
    return {
      swiperOptions: {
        slidesPerView: 5,
        loop: true,
        speed: 1000,
        spaceBetween: 20,
        autoplay: {
          delay: 3000,
          disableOnInteraction: false,
        },
        pagination: {
          el: ".swiper-pagination",
          type: "bullets",
          clickable: true,
        },

        // Responsive breakpoints
        breakpoints: {
          1024: {
            slidesPerView: 5,
          },
          768: {
            slidesPerView: 2,
          },
          640: {
            slidesPerView: 2,
          },
          320: {
            slidesPerView: 1,
          },
        },
      },
    };
  },
};
</script>

<style scoped>
</style>
