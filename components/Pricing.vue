<template>
  <section class="pb-90 mt-3" id='pricing'>
      <div class="container">
          <div class="row justify-content-center">
              <div class="col-md-12 col-lg-8">
                  <div class="section-title text-center" style="padding-top: 40px;">
                      <h2>Sample Text</h2>
                  </div>
              </div>
          </div>

          <div class="row">
              <div class="col-12">
                  <div class="price-nav-wrap">
                      <div class="price--nav-inner">
                          <nav>
                              <div @click="handleToggle" class="nav info-tabs">
                                  <a :class="`price--nav-item ${month ? 'active show' : ''}`" id="nav-contact-tab" data-toggle="tab" href="#month">Sample Tab 1</a>
                                  <a :class="`price--nav-item ${year ? 'active show' : ''}`" href="#year">Sample Tab 2</a>
                              </div>
                          </nav>
                      </div>
                  </div>

                  <div class="tab-content price-content">
                      <div :class="`tab-pane fade ${month ? 'active show' : ''}`" role="tabpanel">
                          <div class="row" style="border: 4px solid #f7f6f9;">
                              <div class="col-md-12 col-lg-12">
                                  <div class="single-price-plan text-left">
                                    <ul v-for="(item, index) in listFirstItem" :key="index">
                                      <li @click="toggleShowLocation(index)" :class="`list-item ${currentItem === index ? 'active' : ''}`">
                                        <span style="color: red;">✦</span>
                                        <span>{{ item.text }}</span>
                                      </li>
                                    </ul>
                                  </div>
                              </div>

                              <!-- <div class="col-md-6 col-lg-6">
                                  <div class="single-price-plan text-left">
                                    <ul v-for="(item, index) in listSecondItem" :key="index">
                                      <li @click="toggleShowLocation(index)" :class="`list-item ${currentItem === index ? 'active' : ''}`">
                                        <span style="color: red;">✦</span>
                                        <span>{{ item.text }}</span>
                                      </li>
                                    </ul>
                                  </div>
                              </div> -->
                          </div>
                      </div>

                      <div :class="`tab-pane fade ${year ? 'active show' : ''}`" role="tabpanel">
                          <div class="row" style="border: 4px solid #f7f6f9;">
                              <div class="col-md-12 col-lg-12">
                                  <div class="single-price-plan text-left">
                                    <ul v-for="(item, index) in listThirdItem" :key="index">
                                      <li @click="toggleShowLocation(index)" :class="`list-item ${currentItem === index ? 'active' : ''}`">
                                        <span style="color: red;">✦</span>
                                        <span>{{ item.text }}</span>
                                      </li>
                                    </ul>
                                  </div>
                              </div>

                              <!-- <div class="col-md-6 col-lg-6">
                                  <div class="single-price-plan text-left">
                                    <ul v-for="(item, index) in listFourthItem" :key="index">
                                      <li @click="toggleShowLocation(index)" :class="`list-item ${currentItem === index ? 'active' : ''}`">
                                        <span style="color: red;">✦</span>
                                        <span>{{ item.text }}</span>
                                      </li>
                                    </ul>
                                  </div>
                              </div> -->
                          </div>
                      </div>
                  </div>
              </div>
          </div>

          <div v-if="isShowLocations" class="row mt-3">
            <div
              @click="toggleShowStatistic(1)"
              :class="`col text-center location-tab ${currentTab == 1 ? 'active show' : ''}`"
            >
              <img v-if="currentTab === 1" src="https://cdn-icons-png.flaticon.com/512/684/684908.png" alt="" style="width: 24px; height: 24px;">
              <span>Hà Nội</span>
            </div>

            <div
              @click="toggleShowStatistic(2)"
              :class="`col text-center location-tab ${currentTab == 2 ? 'active show' : ''}`"
            >
              <img v-if="currentTab === 2" src="https://cdn-icons-png.flaticon.com/512/684/684908.png" alt="" style="width: 24px; height: 24px;">
              <span>Huế</span>
            </div>

            <div
              @click="toggleShowStatistic(3)"
              :class="`col text-center location-tab ${currentTab == 3 ? 'active show' : ''}`"
            >
              <img v-if="currentTab === 3" src="https://cdn-icons-png.flaticon.com/512/684/684908.png" alt="" style="width: 24px; height: 24px;">
              <span>Đà Nẵng</span>
            </div>

            <div
              @click="toggleShowStatistic(4)"
              :class="`col text-center location-tab ${currentTab == 4 ? 'active show' : ''}`"
            >
              <img v-if="currentTab === 4" src="https://cdn-icons-png.flaticon.com/512/684/684908.png" alt="" style="width: 24px; height: 24px;">
              <span>Cần Thơi</span>
            </div>

            <div
              @click="toggleShowStatistic(5)"
              :class="`col text-center location-tab ${currentTab == 5 ? 'active show' : ''}`"
            >
              <img v-if="currentTab === 5" src="https://cdn-icons-png.flaticon.com/512/684/684908.png" alt="" style="width: 24px; height: 24px;">
              <span>TP. Hồ Chí Minh</span>
            </div>
          </div>

          <div v-if="isShowStatistic" class="row mt-3">
            <div class="col-md-6 col-lg-6 text-center">
              <span>Năm 2022</span>

              <div class="row mt-3">
                <div class="col">
                  <div class="fake-chart">
                    <p>100% đúng hạn</p>
                  </div>
                </div>

                <div class="col text-left">
                  <h5>Tổng HS nộp: 5.486.427</h5>
                  <h6>Giải quyết: 5.303.821 hồ sơ</h6>
                  <h6>Đúng hạn: 5.303.821 hồ sơ</h6>
                </div>
              </div>
            </div>

            <div class="col-md-6 col-lg-6 text-center">
              <span>Tình hình</span>

              <div class="statistic-card mt-3">
                <swiper :options="swiperOptions">

                  <swiper-slide>
                    <div class="right-handed-card">
                      <span>Tháng 01/2022</span><br>
                      <span>Text</span><br>
                    </div>
                  </swiper-slide>

                  <swiper-slide>
                    <div class="right-handed-card">
                      <span>Tháng 02/2022</span><br>
                      <span>Text</span><br>
                    </div>
                  </swiper-slide>

                  <swiper-slide>
                    <div class="right-handed-card">
                      <span>Tháng 03/2022</span><br>
                      <span>Text</span><br>
                    </div>
                  </swiper-slide>

                  <swiper-slide>
                    <div class="right-handed-card">
                      <span>Tháng 04/2022</span><br>
                      <span>Text</span><br>
                    </div>
                  </swiper-slide>
                </swiper>
              </div>
            </div>
          </div>
      </div>
  </section>
</template>

<script>
  import { Swiper, SwiperSlide, directive } from 'vue-awesome-swiper'
  import 'swiper/css/swiper.css'

  export default {
    name: "Pricing",
    components: {
      Swiper,
      SwiperSlide
    },
    directives: {
      swiper: directive
    },
    data(){
      return {
        month: true,

        year: false,

        isShowLocations: false,

        currentTab: '',

        currentItem: '',

        isShowStatistic: false,

        swiperOptions: {
          slidesPerView : 3,
          loop: true,
          speed: 1000,
          spaceBetween : 30,
          autoplay: {
              delay: 3000,
              disableOnInteraction: false
          },
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
        },

        listFirstItem: [
          {
            id: 1,
            text: 'Example Text 1',
          },
          {
            id: 2,
            text: 'Example Text 2',
          },
          {
            id: 3,
            text: 'Example Text 3',
          },
          {
            id: 4,
            text: 'Example Text 4',
          },
          {
            id: 5,
            text: 'Example Text 5',
          },
        ],

        listSecondItem: [
          {
            id: 1,
            text: 'Example Text 1',
          },
          {
            id: 2,
            text: 'Example Text 2',
          },
          {
            id: 3,
            text: 'Example Text 3',
          },
          {
            id: 4,
            text: 'Example Text 4',
          },
          {
            id: 5,
            text: 'Example Text 5',
          },
        ],
        

        listThirdItem: [
          {
            id: 1,
            text: 'Example Text 1',
          },
          {
            id: 2,
            text: 'Example Text 2',
          },
          {
            id: 3,
            text: 'Example Text 3',
          },
          {
            id: 4,
            text: 'Example Text 4',
          },
          {
            id: 5,
            text: 'Example Text 5',
          },
        ],
        

        listFourthItem: [
          {
            id: 1,
            text: 'Example Text 1',
          },
          {
            id: 2,
            text: 'Example Text 2',
          },
          {
            id: 3,
            text: 'Example Text 3',
          },
          {
            id: 4,
            text: 'Example Text 4',
          },
          {
            id: 5,
            text: 'Example Text 5',
          },
        ]
      }
    },
    methods: {

      handleToggle(){
          const month = this.month;
          const year = this.year;

          if(month){
              this.year = true;
              this.month = false;
              this.isShowLocations = false;
          }
          if(year){
            this.year = false;
            this.month = true;
            this.isShowLocations = false;
          }

      },

      toggleShowLocation(index) {
        this.isShowLocations = true;
        this.isShowStatistic = false;
        this.currentTab = '';
        this.currentItem = index;
      },

      toggleShowStatistic(tab) {
        this.currentTab = tab;
        this.isShowStatistic = true;
      }
    }
  }
</script>

<style scoped>

</style>
