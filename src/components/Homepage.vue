<template>
  <div class="Homepage_main_container">
    <section class="Homepage_container_sorties">
      <SectionPreviewSortie />
    </section>
    <section class="Homepage_container_creer_sortie">
      <SectionCreerSortie />
    </section>
  </div>
</template>

<script>
import SectionPreviewSortie from "./SectionMesSorties.vue";
import SectionCreerSortie from "./SectionCreerSortie.vue";
// import Footer from "./Footer.vue";

export default {
  name: "Homepage",

  components: {
    SectionPreviewSortie,
    SectionCreerSortie,
    // Footer
  },

  props: {
    msg: String,
  },
  data() {
    return {};
  },
};
</script>

<style scoped lang="scss">
$orange: #f9bb3d;
@font-face {
  font-family: "OS_exbold";
  src: url("../assets/font/OpenSans-ExtraBold.ttf");
}
@font-face {
  font-family: "OS_light";
  src: url("../assets/font/OpenSans-Light.ttf");
}
@font-face {
  font-family: "OS_medium";
  src: url("../assets/font/OpenSans-Medium.ttf");
}
@font-face {
  font-family: "OS_regular";
  src: url("../assets/font/OpenSans-Regular.ttf");
}
@font-face {
  font-family: "OS_semiBold";
  src: url("../assets/font/OpenSans-SemiBold.ttf");
}

@media screen and (min-width: 500px) {
  .Homepage_main_container {
    padding: 80px 0px 30px 0px;
    margin: 0px;
    display: Flex;
    flex-direction: column;
    align-items: center;
    background-image: url("~@/assets/images/mobile_man_running.jpg");
    background-size: cover;
    .Homepage_container_sorties {
      width: 100%;
      min-height: 200px;
      padding: 20px 0px;
      margin: 10% 0% 10% 0%;
      background: linear-gradient(
        34deg,
        rgb(244, 226, 11) 7%,
        rgba(250, 164, 4, 0.5) 46%,
        rgba(255, 0, 0, 0.5) 100%
      );
      display: grid;
      justify-content: center;
      align-items: center;
    }
    .Homepage_container_creer_sortie {
      width: 90%;
      display: grid;
      padding: 10px;
      justify-content: center;
      align-content: center;
      width: 100%;

      background-color: white;
    }
  }
}

// RESPONSIVE MOBILE
@media screen and (max-width: 500px) {
  .Homepage_main_container {
    width: 100vw;
    padding: 80px 0px 30px 0px;
    margin: 0px;
    display: Flex;
    flex-direction: column;
    align-items: center;
    background-image: url("~@/assets/images/mobile_man_running.jpg");
    background-size: cover;
    .Homepage_container_sorties {
      min-height: 100px;
      padding: 20px 5px;
      margin: 10% 0% 10% 0%;
      background: linear-gradient(
        34deg,
        rgb(244, 226, 11) 7%,
        rgba(250, 164, 4, 0.5) 46%,
        rgba(255, 0, 0, 0.5) 100%
      );
      display: grid;
      justify-content: center;
      align-items: center;
    }
    .Homepage_container_creer_sortie {
      display: grid;
      padding: 10px;
      justify-content: center;
      align-content: center;
      width: 100%;

      background-color: white;
    }
  }
}


</style>
