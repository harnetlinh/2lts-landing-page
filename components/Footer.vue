<template>
    <div>
      <footer class="footer">
          <div class="footerbg">
          <img src="/assets/img/footer-bg.png" alt="">
          </div>
          <div class="footer-top pt-120 pb-110">
              <div class="container">
                  <div class="row">
                      <div class="col-lg-3 col-sm-6">
                          <!-- footer widget -->
                          <div class="footer-widget">
                              <div class="footer-logo">
                                  <a href="/"><img src="/assets/img/logo@op.png" alt="" width="50%"></a>
                              </div>
                              <!-- footer social area -->
                              <div class="footer-social-area">
                                  <ul class="social-icons social-icons-light nav">
                                      <li><a href="#" target="_blank"><i class="fa fa-facebook-f"></i></a></li>
                                      <li><a href="#" target="_blank"><i class="fa fa-twitter"></i></a></li>
                                      <li><a href="#" target="_blank"><i class="fa fa-google-plus"></i></a></li>
                                      <li><a href="#" target="_blank"><i class="fa fa-linkedin"></i></a></li>
                                  </ul>
                              </div>
                              <!-- End of footer social area -->
                          </div>
                          <!--End of footer widget -->
                      </div>

                      <div class="col-lg-3 col-sm-6">
                          <div class="footer-widget">
                              <!-- widget header -->
                              <div class="widget-header">
                                  <h5>Địa chỉ</h5>
                              </div>
                              <!-- widget header -->
                              <div class="widget-body">
                                  <ul class="address-list">
                                      <li>
                                          <span><i class="fa  fa-phone-square"></i></span>
                                          888 999 0000
                                      </li>
                                      <li>
                                          <span><i class="fa  fa-envelope"></i></span>
                                          needhelp@2lts.com
                                      </li>
                                      <li>
                                          <span><i class="fa  fa-map"></i></span>
                                          Hà Nội, Việt Nam
                                      </li>
                                  </ul>
                              </div>
                          </div>
                      </div>
                      <div class="col-lg-3 col-sm-6">
                          <div class="footer-widget">
                              <!-- widget header -->
                              <div class="widget-header">
                                  <h5>Thông tin</h5>
                              </div>
                              <!-- widget header -->
                          </div>

                          <div class="widget-body">
                              <div class="extra-link">
                                  <div class="link-left">
                                      <ul>
                                          <li><a href="#">Trang chủ</a></li>
                                          <li><a href="#">Chúng tôi</a></li>
                                          <li><a href="#">Sản phẩm</a></li>
                                          <li><a href="#">Thông tin dịch vụ</a></li>
                                      </ul>
                                  </div>

                              </div>
                          </div>
                      </div>

                      <div class="col-lg-3 col-sm-6">
                          <div class="footer-widget">
                              <div class="widget-body">
                                  <div class="twetter-post-inner">
                                      <div class="footer-post-details">
                                          Đồng hành hành chính công cùng bạn
                                      </div>
                                      <div class="twetter-post">
                                          <span><i class="fa fa-twitter"></i></span>
                                          2LTS
                                      </div>
                                  </div>
                              </div>
                          </div>
                      </div>
                  </div>
              </div>
          </div>
          <div class="footer-bottom">
              <div class="footer-text text-center">
                  <p>© copyright 2023 by 2LTS</p>
              </div>
          </div>

      </footer>

      <!-- back to top -->
      <div @click="scrollTop" :class="`back-to-top ${scrollBtn ? 'show' : ''}`">
          <a href="#"><i class="fa fa-chevron-up"></i></a>
      </div>

    </div>
</template>

<script>
    export default {
      name: "Footer",
      data(){
        return {
          scrollBtn: false
        }
      },
      mounted() {
        window.addEventListener('scroll', this.handleScroll);
      },

      methods: {

        handleScroll () {

          if (window.scrollY > 70) {
            this.scrollBtn = true
          }
          else if (window.scrollY < 70) {
            this.scrollBtn = false
          }
        },

        scrollTop () {
            window.scrollTo(0, 0);
        }


      }
    }
</script>

<style scoped>

</style>
