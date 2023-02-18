<template>
  <div>
  <section class="pb-110 mt-5" id='features'>
      <div class="">
          <div class="row justify-content-center">
              <div class="col-md-12 col-lg-12 col-xl-12">
                  <!-- section title -->
                  <div class="text-center">
                      <h2>Về chúng tôi</h2>
                      <div class="w-100">
                        <img width="100%" src="../static/assets/img/2LTS_3.png" alt="">
                      </div>
                  </div>
                  <!-- End of section title -->
              </div>
          </div>
          <div class="row justify-content-center">
              <div class="col-xl-10 col-lg-12">
                  <div class="feature-carousel owl-carousel">

                    <swiper :options="swiperOptions">

                      <swiper-slide>
                      <!-- single feature inner -->
                      <div class="single-feature-inner text-center">
                          <div class="feature-icon"><img src="/assets/img/icons/project-management.svg" class="svg" alt=""></div>
                          <h5>New Artwork<br> Unveiled</h5>
                          <p>There are many variations of passages of lorem Ipsum but majority have suffered.</p>
                      </div>
                      <!-- End of single feature inner -->
                      </swiper-slide>

                      <swiper-slide>
                      <!-- single feature inner -->
                      <div class="single-feature-inner text-center">
                          <div class="feature-icon"><img src="/assets/img/icons/solution.svg" class="svg" alt=""></div>
                          <h5>Company Growth<br> Strategy</h5>
                          <p>There are many variations of passages of lorem Ipsum but majority have suffered.</p>
                      </div>
                      <!-- End of single feature inner -->
                      </swiper-slide>

                      <swiper-slide>
                      <!-- single feature inner -->
                      <div class="single-feature-inner text-center">
                          <div class="feature-icon"><img src="/assets/img/icons/planning.svg" class="svg" alt=""></div>
                          <h5>Perfect Application Intergration</h5>
                          <p>There are many variations of passages of lorem Ipsum but majority have suffered.</p>
                      </div>
                      <!-- End of single feature inner -->
                      </swiper-slide>

                      <swiper-slide>
                      <!-- single feature inner -->
                      <div class="single-feature-inner text-center">
                          <div class="feature-icon"><img src="/assets/img/icons/goal.svg" class="svg" alt=""></div>
                          <h5>Creative App<br>Display</h5>
                          <p>There are many variations of passages of lorem Ipsum but majority have suffered.</p>
                      </div><!-- End of single feature inner -->
                      </swiper-slide>
                      <div class="swiper-pagination" slot="pagination"></div>
                    </swiper>
                  </div><!--/.feature-carousel-->
              </div><!--/.col-->
          </div><!--/.row-->
      </div><!--/.container-->
  </section>
  </div>
</template>

<script>
  import { Swiper, SwiperSlide, directive } from 'vue-awesome-swiper'
  import 'swiper/css/swiper.css'

  export default {
    name: "Features",
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
          slidesPerView : 3,
          loop: true,
          speed: 1000,
          spaceBetween : 30,
          autoplay: {
              delay: 3000,
              disableOnInteraction: false
          },
          pagination: {
            el: '.swiper-pagination',
            type: 'bullets',
            clickable: true
          },

          // Responsive breakpoints
          breakpoints: {
            1024:{
                slidesPerView : 3
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
