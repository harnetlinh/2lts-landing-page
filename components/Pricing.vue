<template>
  <section class="pb-90 mt-3" id='pricing'>
      <div class="container">
          <div class="row justify-content-center">
              <div class="col-md-12 col-lg-8">
                  <div class="section-title text-center" style="padding-top: 40px;">
                      <h2>Tra cứu dịch vụ</h2>
                  </div>
              </div>
          </div>

          <div class="row">
              <div class="col-12">
                  <div class="price-nav-wrap">
                      <div class="price--nav-inner">
                          <nav>
                              <div @click="handleToggle" class="nav info-tabs">
                                  <a :class="`price--nav-item ${month ? 'active show' : ''}`" id="nav-contact-tab" data-toggle="tab" href="#month">Công dân</a>
                                  <a :class="`price--nav-item ${year ? 'active show' : ''}`" href="#year">Doanh nghiệp</a>
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
              <span>Hoàn Kiếm</span>
            </div>

            <div
              @click="toggleShowStatistic(2)"
              :class="`col text-center location-tab ${currentTab == 2 ? 'active show' : ''}`"
            >
              <img v-if="currentTab === 2" src="https://cdn-icons-png.flaticon.com/512/684/684908.png" alt="" style="width: 24px; height: 24px;">
              <span>Đống Đa</span>
            </div>

            <div
              @click="toggleShowStatistic(3)"
              :class="`col text-center location-tab ${currentTab == 3 ? 'active show' : ''}`"
            >
              <img v-if="currentTab === 3" src="https://cdn-icons-png.flaticon.com/512/684/684908.png" alt="" style="width: 24px; height: 24px;">
              <span>Ba Đình</span>
            </div>

            <div
              @click="toggleShowStatistic(4)"
              :class="`col text-center location-tab ${currentTab == 4 ? 'active show' : ''}`"
            >
              <img v-if="currentTab === 4" src="https://cdn-icons-png.flaticon.com/512/684/684908.png" alt="" style="width: 24px; height: 24px;">
              <span>Hai Bà Trưng</span>
            </div>

            <div
              @click="toggleShowStatistic(5)"
              :class="`col text-center location-tab ${currentTab == 5 ? 'active show' : ''}`"
            >
              <img v-if="currentTab === 5" src="https://cdn-icons-png.flaticon.com/512/684/684908.png" alt="" style="width: 24px; height: 24px;">
              <span>Thanh Xuân</span>
            </div>
          </div>

          <div v-if="isShowStatistic" class="row mt-3">
            <div class="col-md-6 col-lg-6 text-center">
              <span>Hôm nay, 20/02/2023</span>

              <div class="row mt-3">
                <div class="col">
                  <div :class="'fake-chart ' + (choosen_prediction.co_dong ? 'bg-danger text-white':'bg-success text-white' )">
                    <p>
                      {{ choosen_prediction.co_dong ? "ĐÔNG" : "KHÔNG ĐÔNG" }}
                    </p>
                  </div>
                </div>

                <div class="col text-left">
                  <h6>Số nhân viên : {{ choosen_prediction.so_nhan_vien }} người </h6>
                  <h6>Đang làm hồ sơ: {{ choosen_prediction.dang_lam  }} người</h6>
                  <h6>Đang chờ: {{ choosen_prediction.dang_cho  }} người</h6>
                </div>
              </div>
            </div>

            <div class="col-md-6 col-lg-6 text-center">
              <span>Dự báo tình trạng</span>

              <div class="statistic-card mt-3">
                <swiper :options="swiperOptions">

                  <swiper-slide v-for="(sw,index) in choosen_prediction.predictions" :key="index">
                    <div :class="'right-handed-card ' + (sw.co_dong ? 'bg-danger text-white':'bg-success text-white' )">
                      <span>Ngày {{ sw.date }}</span><br>
                      <span>{{ sw.co_dong ? "ĐÔNG" : "KHÔNG ĐÔNG" }}</span><br>
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
        choosen_prediction: {},
        predictions:[
          {
            so_nhan_vien: 20,
            dang_lam: 20,
            dang_cho: 0,
            co_dong: false,
            predictions: [
              {
                date: "21/02/2023",
                co_dong: true
              },
              {
                date: "22/02/2023",
                co_dong: true
              },
              {
                date: "23/02/2023",
                co_dong: false,
              },
              {
                date: "24/02/2023",
                co_dong: false,
              },
              {
                date: "27/02/2023",
                co_dong: true,
              },
              {
                date: "28/02/2023",
                co_dong: true,
              },
            ]
          },
          {
            so_nhan_vien: 20,
            dang_lam: 20,
            dang_cho: 30,
            co_dong: true,
            predictions: [
              {
                date: "21/02/2023",
                co_dong: false
              },
              {
                date: "22/02/2023",
                co_dong: true
              },
              {
                date: "23/02/2023",
                co_dong: true,
              },
              {
                date: "24/02/2023",
                co_dong: false,
              },
              {
                date: "27/02/2023",
                co_dong: false,
              },
              {
                date: "28/02/2023",
                co_dong: true,
              },
            ]
          },
          {
            so_nhan_vien: 20,
            dang_lam: 10,
            dang_cho: 0,
            co_dong: false,
            predictions: [
              {
                date: "21/02/2023",
                co_dong: false
              },
              {
                date: "22/02/2023",
                co_dong: true
              },
              {
                date: "23/02/2023",
                co_dong: true,
              },
              {
                date: "24/02/2023",
                co_dong: false,
              },
              {
                date: "27/02/2023",
                co_dong: true,
              },
              {
                date: "28/02/2023",
                co_dong: true,
              },
            ]
          },
          {
            so_nhan_vien: 20,
            dang_lam: 10,
            dang_cho: 0,
            co_dong: false,
            predictions: [
              {
                date: "21/02/2023",
                co_dong: false
              },
              {
                date: "22/02/2023",
                co_dong: false
              },
              {
                date: "23/02/2023",
                co_dong: false,
              },
              {
                date: "24/02/2023",
                co_dong: false,
              },
              {
                date: "27/02/2023",
                co_dong: true,
              },
              {
                date: "28/02/2023",
                co_dong: false,
              },
            ]
          },
          {
            so_nhan_vien: 20,
            dang_lam: 20,
            dang_cho: 20,
            co_dong: true,
            predictions: [
              {
                date: "21/02/2023",
                co_dong: false
              },
              {
                date: "22/02/2023",
                co_dong: false
              },
              {
                date: "23/02/2023",
                co_dong: false,
              },
              {
                date: "24/02/2023",
                co_dong: true,
              },
              {
                date: "27/02/2023",
                co_dong: true,
              },
              {
                date: "28/02/2023",
                co_dong: true,
              },
            ]
          },

        ],

        currentDate: '',

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
              disableOnInteraction: true
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
            text: 'Hộ tịch',
          },
          {
            id: 2,
            text: 'Chứng thực',
          },
          {
            id: 3,
            text: 'Bảo trợ',
          },
          {
            id: 4,
            text: 'Xây dựng',
          },
          {
            id: 5,
            text: 'Y tế',
          },
        ],

        listSecondItem: [
          {
            id: 1,
            text: 'Khởi sự',
          },
          {
            id: 2,
            text: 'Công thương',
          },
          {
            id: 3,
            text: 'Thương mại',
          },
          {
            id: 4,
            text: 'Sở hữu trí tuệ',
          },
          {
            id: 5,
            text: 'Xuất bản',
          },
        ],


        listThirdItem: [
          {
            id: 1,
            text: 'Khởi sự',
          },
          {
            id: 2,
            text: 'Công thương',
          },
          {
            id: 3,
            text: 'Thương mại',
          },
          {
            id: 4,
            text: 'Sở hữu trí tuệ',
          },
          {
            id: 5,
            text: 'Xuất bản',
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
    created() {
      this.getCurrentDate();
    },
    methods: {
      getCurrentDate(){
        const today = new Date();
        const yyyy = today.getFullYear();
        let mm = today.getMonth() + 1; // Months start at 0!
        let dd = today.getDate();

        if (dd < 10) dd = '0' + dd;
        if (mm < 10) mm = '0' + mm;

        this.currentDate = dd + '/' + mm + '/' + yyyy;
      },
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
        console.log(tab)
        this.currentTab = tab;
        this.isShowStatistic = true;
        this.choosen_prediction = this.predictions[tab - 1]
        console.log(this.choosen_prediction)
      }
    }
  }
</script>

<style scoped>

</style>
