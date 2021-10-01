<template>
  <div class="Home_main_container">
    <Header />
  <Homepage/>
    <Footer />
  </div>
</template>

<script>
import Header from "../components/Header.vue";
import Footer from "../components/Footer.vue";
import Homepage from "../components/Homepage.vue";

export default {
  name: "Home",

  components: {
    Header,
    Footer,
    Homepage
  },

  props: {
    msg: String,
  },
  data() {
    return {};
  },
};
</script>
<style lang="scss" scoped>
.Home_main_container{
  widows: 100vw;
}
</style>



