<template>
  <section class="pb-120" id="gia-tri-cot-loi">
      <div class="ontainer-fluid">
          <div class="row justify-content-center">
              <div class="col-md-12 col-lg-12 col-xl-12">
                  <!-- partner carosel inner -->
                  <div class="w-100">
                    <img width="100%" src="../static/assets/img/2LTS_9.png" alt="">
                  </div>
                  <div class="partner-carousel-wrap d-none">
                      <div class="partner-carousel owl-carousel">

                        <swiper :options="swiperOptions">

                          <swiper-slide>
                            <!-- single partner -->
                            <div class="single-partner">
                                <img src="/assets/img/partner2.png" alt="">
                            </div>
                            <!-- End of single partner -->
                          </swiper-slide>

                          <swiper-slide>
                            <!-- single partner -->
                            <div class="single-partner">
                                <img src="/assets/img/partner2.png" alt="">
                            </div>
                            <!-- End of single partner -->
                          </swiper-slide>

                          <swiper-slide>
                            <!-- single partner -->
                            <div class="single-partner">
                                <img src="/assets/img/partner2.png" alt="">
                            </div>
                            <!-- End of single partner -->
                          </swiper-slide>

                          <swiper-slide>
                            <!-- single partner -->
                            <div class="single-partner">
                                <img src="/assets/img/partner2.png" alt="">
                            </div>
                            <!-- End of single partner -->
                          </swiper-slide>

                        </swiper>
                      </div>
                  </div>
                  <!--End of  partner carosel inner -->
              </div>
          </div>
      </div>
    </section>
</template>

<script>
  import { Swiper, SwiperSlide, directive } from 'vue-awesome-swiper';
  import 'swiper/css/swiper.css';

    export default {
      name: "ClientsLogo",
      components: {
        Swiper,
        SwiperSlide
      },
      directives: {
        swiper: directive
      },
      data() {
        return {
          swiperOptions: {
            slidesPerView : 5,
            loop: true,
            speed: 1000,
            spaceBetween : 30,
            autoplay: {
                delay: 3000,
                disableOnInteraction: false
            },

            // Responsive breakpoints
            breakpoints: {
              1024:{
                  slidesPerView : 5
              },
              768:{
                  slidesPerView : 2
              },
              640:{
                  slidesPerView : 2
              },
              320:{
                  slidesPerView : 1
              }
            }
          }
        }
      },
    }
</script>

<style scoped>

</style>
