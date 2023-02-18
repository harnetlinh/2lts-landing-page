<template>
  <div class="banner-area-inner">
    <div class="banner-inner-area banner-area1">
        <div style="container-fluid">
            <div class="row align-items-center">
                <div class="col-lg-4 col-md-5 col-xl-5">
                    <!-- banner text -->
                    <div class="banner-text-inner" style="margin-left:100px">
                        <h1 style="width:100%">Hành chính đúng <br>thời điểm</h1>
                        <a href="#pricing" class="btn">Tra cứu dịch vụ</a>
                        <a href="#" class="btn">Ứng dụng quản lý</a>
                    </div>
                    <!-- banner text -->
                </div>
                <div class="col-lg-8 col-md-7 col-xl-7">
                    <!-- banner image-->
                    <div class="banner-image" style="margin-right:30px">
                        <img src="/assets/img/banner/mockup.png" alt="" width="100%">
                    </div>
                    <!--End of banner image-->
                </div>
            </div>
        </div>
    </div>
      </div>
</template>

<script>
    export default {
        name: "BannerOne"
    }
</script>

<style scoped>
.banner-image {
  height: calc(100vh - 92px);
}
</style>
