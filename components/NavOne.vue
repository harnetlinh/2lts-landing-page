<template>
  <header class="header" id="header-section">
    <!-- Start Header Navbar-->
    <div :class="`main-header ${sticky ? 'sticky fadeInDown' : ''}`">
      <div class="main-menu-wrap">
        <div class="container">
          <div class="row align-items-center">
            <div class="col-xl-2 col-lg-2 col-md-3 col-4">
              <!-- Logo -->
              <div class="logo">
                <nuxt-link to="/">
                  <img src="/assets/img/logo.png" alt="jironis" width="30%" />
                </nuxt-link>
              </div>
              <!-- End of Logo -->
            </div>
            <div class="col-xl-9 col-lg-9 col-md-9 col-9 menu-button">
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
                        <li>
                          <a href="#">Chúng tôi</a>
                          <ul>
                            <li>
                              <a href="#features">Về chúng tôi</a>
                            </li>
                            <li>
                              <a href="#app">Tầm nhìn sứ mệnh</a>
                            </li>
                            <li>
                              <a href="#gia-tri-cot-loi">Giá trị cốt lõi</a>
                            </li>
                          </ul>
                          <!-- <a href="#features">Chúng tôi</a> -->
                        </li>
                        <li><a href="#pricing"> Tra cứu dịch vụ </a></li>
                      </ul>
                    </div>
                    <!-- End of Header-menu -->
                  </nav>
                </div>
              </div>
            </div>
            <div class="col-lg-1 col-md-1 col-sm-1 d-md-block d-none">
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
  data() {
    return {
      sticky: false,
    };
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);

    this.mobileMenu();
  },

  methods: {
    handleScroll() {
      if (window.scrollY > 70) {
        this.sticky = true;
      } else if (window.scrollY < 70) {
        this.sticky = false;
      }
    },

    mobileMenu() {
      //Mobile Menu Toggle
      let mainNavToggler = document.querySelector("#menu-button");
      let mainNav = document.querySelector(".main-nav");

      mainNavToggler.addEventListener("click", function () {
        //mainNavToggler.classList.add('menu-opened');
        mainNav.style.display =
          mainNav.style.display != "block" ? "block" : "none";
      });
    },
  },
};
</script>

<style scoped>
</style>
