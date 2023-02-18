<template>
  <div>
  <section class="pb-110 mt-5" id='features'>
    <div class="row justify-content-center">
        <div class="col-md-12 col-lg-12 col-xl-12">
            <!-- section title -->
            <div class="text-center">
                <div class="w-100">
                  <img width="100%" src="../static/assets/img/2LTS_3.png" alt="">
                </div>
            </div>
            <!-- End of section title -->
        </div>
    </div>

      <div class="container">
          <div class="row justify-content-center">
              <div class="col-xl-10 col-lg-12">
                  <div class="feature-carousel owl-carousel">

                    <swiper :options="swiperOptions">

                      <swiper-slide>
                        <div class="single-feature-inner text-center">
                            <img
                              style="object-fit: contain;"
                              src="https://lh3.googleusercontent.com/u/0/drive-viewer/AAOQEOSISuYrVjDtqhZzorbGad07am7nUuUdjWnRfxBexZXlXH7rjj5-TzZgqHovb9n4K4tPUUNTTkrbIJ036-8NfW_S3yP2LA=w1920-h969"
                              class="svg"
                              alt=""
                            >
                        </div>
                      </swiper-slide>

                      <swiper-slide>
                        <div class="single-feature-inner text-center">
                            <img
                              style="object-fit: contain;"
                              src="https://lh3.googleusercontent.com/u/0/drive-viewer/AAOQEORFaa-Za2e68WCSJMNdlRulty_4dYZ2wCKN0Ad9Mmtp0ZUqPG0Reqrkxb_sIJGl8KGwsLymV6u-csV7knlLjxFOrexHPQ=w1920-h969"
                              class="svg"
                              alt=""
                            >
                        </div>
                      </swiper-slide>

                      <swiper-slide>
                        <div class="single-feature-inner text-center">
                            <img
                              style="object-fit: contain;"
                              src="https://lh3.googleusercontent.com/u/0/drive-viewer/AAOQEOQS0oFTLTA6PsKTeLUBv928yiOyww2bIFJnCe2LV71HAhcOLSiE8TCQW6ShI66vKQrRwrntteZ244iBkyKNXw4gLPHldQ=w1920-h969"
                              class="svg"
                              alt=""
                            >
                        </div>
                      </swiper-slide>

                      <swiper-slide>
                        <div class="single-feature-inner text-center">
                            <img
                              style="object-fit: contain;"
                              src="https://lh3.googleusercontent.com/u/0/drive-viewer/AAOQEOQNEGjVTIFtamYmvO3G-oe0DUWfqPq8nF7cHizzbRRBjYndK5MNbdzUYQz8TXEKx5B1dSoX7amkfF-dpnZP29p6ez4s=w1920-h969"
                              class="svg"
                              alt=""
                            >
                        </div>
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
