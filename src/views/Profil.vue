<template>
  <div class="Home_main_container">
    <Header />
    <FicheProfil/>
    <Footer />
  </div>
</template>

<script>
import Header from "../components/Header.vue";
import Footer from "../components/Footer.vue";
import FicheProfil from "../components/FicheProfil.vue";

export default {
  name: "Profil",

  components: {
    Header,
    Footer,
    FicheProfil,
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
.Home_main_container {
width: 100vw;
}
</style>
