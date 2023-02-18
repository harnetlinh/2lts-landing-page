<template>
  <div>
    <NavOne />
    <BannerOne />
    <Features />
    <Screenshots />
    <ClientsLogo />
    <ServiceOne />
    <ServiceTwo />
    <ServiceThree />
    <ServiceFour />
    <Pricing />
    <Footer />
  </div>

</template>
<script>
  import NavOne from "../components/NavOne";
  import BannerOne from "../components/BannerOne";
  import Footer from "../components/Footer";
  import Features from "../components/Features";
  import Counter from "../components/Counter";
  import ServiceTwo from "../components/ServiceTwo";
  import ServiceOne from "../components/ServiceOne";
  import ServiceThree from "../components/ServiceThree";
  import ServiceFour from "../components/ServiceFour";
  import Video from "../components/Video";
  import Screenshots from "../components/Screenshots";
  import Pricing from "../components/Pricing";
  import Testimonial from "../components/Testimonial";
  import ClientsLogo from "../components/ClientsLogo";
  import BlogHome from "../components/BlogHome";
  import DownloadApp from "../components/DownloadApp";
  export default {
    components: {
      DownloadApp,
      BlogHome,
      ClientsLogo,
      Testimonial,
      Pricing,
      Screenshots,
      Video,
      ServiceOne,
      ServiceTwo,
      ServiceThree,
      ServiceFour,
      Counter,
      Features,
      Footer,
      BannerOne,
      NavOne
    }
  }
</script>
