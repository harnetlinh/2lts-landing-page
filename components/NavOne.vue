<template>
  <header class="header" id="header-section">
          <!-- Start Header Navbar-->
      <div :class="`main-header ${sticky ? 'sticky fadeInDown' : ''}`">
          <div class="main-menu-wrap">
              <div class="container">
                  <div class="row align-items-center">
                      <div class="col-xl-3 col-lg-3 col-md-4 col-6">
                          <!-- Logo -->
                          <div class="logo">
                              <nuxt-link to="/">
                                  <img src="/assets/img/logo.png" alt="jironis" width="15%">
                              </nuxt-link>
                          </div>
                          <!-- End of Logo -->
                      </div>
                      <div class="col-xl-6 col-lg-6 col-md-4 col-6 menu-button">
                          <div class="menu--inner-area clearfix">
                              <div class="menu-wraper">
                                  <nav>
                                      <!-- Header-menu -->
                                      <div class="header-menu dosis">

                                        <div id="menu-button" class="">
                                          <i class="fa fa-bars"></i>
                                        </div>

                                          <ul class="main-nav">
                                              <li class="active">
                                                <a href="#header-section">Trang chủ</a>

                                              </li>
                                              <li><a href="#features">Chúng tôi</a></li>
                                              <li><a href="#app">Sản phẩm</a></li>
                                              <li><a href="#pricing">
                                                Tra cứu dịch vụ
                                              </a></li>
                                          </ul>
                                      </div>
                                      <!-- End of Header-menu -->
                                  </nav>
                              </div>
                          </div>
                      </div>
                      <div class="col-lg-3 col-md-4 col-sm-5 d-md-block d-none">
                          <div class="urgent-call text-right">
                             <a href="#" class="btn">Đăng nhập</a>
                          </div>
                      </div>
                  </div>
              </div>
          </div>
      </div>
      <!-- End Header Navbar-->
  </header>
</template>

<script>
    export default {
      name: "NavOne",
      data(){
        return {
          sticky: false
        }
      },
      mounted() {
        window.addEventListener('scroll', this.handleScroll);

        this.mobileMenu();
      },

      methods: {

        handleScroll () {

          if (window.scrollY > 70) {
            this.sticky = true
          }
          else if (window.scrollY < 70) {
            this.sticky = false
          }
        },

        mobileMenu() {
            //Mobile Menu Toggle
            let mainNavToggler = document.querySelector("#menu-button");
            let mainNav = document.querySelector(".main-nav");

            mainNavToggler.addEventListener("click", function () {
                //mainNavToggler.classList.add('menu-opened');
                mainNav.style.display = ( (mainNav.style.display != "block" ? "block" : "none" ) );
            });
        }

      }
    }
</script>

<style scoped>

</style>
