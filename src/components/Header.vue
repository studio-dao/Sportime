<template>
  <div class="Header_main_container">
    <!-- HEADER -->
    <header class="Header">
      <div class="Header_logo">
        <img src="@/assets/logos/logo_rond.png" alt="picto_logo" />
      </div>
      <div class="Header_salutation">
        <p class="Header_salutation_parag_bonjour">
          BONJOUR
        </p>
        <p class="Header_salutation_parag_name">
          ADAM
        </p>
      </div>
      <a class="Header_profil_lien" href="#"
        ><div class="Header_div_picto_profil">
          <img src="@/assets/pictos/picto_profil.png" alt="picto_profil" />
        </div>
      </a>
    </header>
  </div>
</template>

<script>
export default {
  name: "Header",
  props: {
    msg: String,
  },
  data() {
    return {
      pseudo: "",
      password: "",
    };
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
  .Header_main_container {
    position: fixed;
    width: 100vw;
  }
  .Header {
    display: grid;
    width: 100%;
    background-color: rgba(32, 32, 32, 0.5);
    grid-template-columns: 2fr 3.5fr 2fr;
    .Header_logo {
      display: grid;
      padding: 10px 0px;
      justify-content: center;
      align-items: center;
      img {
        width: 100%;
      }
    }
    .Header_salutation {
      display: grid;
      padding: 10px 0px;
      grid-auto-rows: 40px;
      justify-content: flex-start;
      align-content: center;

      .Header_salutation_parag_bonjour {
        font-family: "OS_exbold";
        margin: 0px;
        text-align: left;
        font-size: 40px;
        color: $orange;
      }
      .Header_salutation_parag_name {
        font-family: "OS_exbold";
        margin: 0px;
        text-align: left;
        font-size: 40px;
        color: $orange;
      }
    }
    .Header_profil_lien {
      display: grid;
      padding: 10px 0px;
      justify-content: center;
      align-content: center;
      justify-items: center;
      align-items: center;
      .Header_div_picto_profil {
        display: grid;
        justify-items: center;
        align-items: center;
      }
      img {
        width: 70%;
      }
    }
  }
}

@media screen and (max-width: 500px) {
  .Header_main_container {
    position: fixed;
    width: 100vw;
  }
  .Header {
    display: grid;
    width: 100%;
    background-color: rgba(32, 32, 32, 0.5);

    grid-template-columns: 2fr 4fr 2fr;
    .Header_logo {
      display: grid;
      padding: 5px;
      justify-content: center;
      align-items: center;
      img {
        width: 80%;
      }
    }
    .Header_salutation {
      display: grid;
      grid-auto-rows: 25px;
      justify-content: flex-start;
      align-content: center;

      .Header_salutation_parag_bonjour {
        font-family: "OS_exbold";
        margin: 0px;
        text-align: left;
        font-size: 1em;
        color: $orange;
      }
      .Header_salutation_parag_name {
        font-family: "OS_exbold";
        margin: 0px;
        text-align: left;
        font-size: 1em;
        color: $orange;
      }
    }
    .Header_profil_lien {
      width: 100%;
      height: 100%;
      .Header_div_picto_profil {
        display: grid;
        height: 100%;
        padding: 2px;
        justify-items: center;
        align-items: center;
        img {
          width: 60%;
        }
      }
    }
  }
}
</style>
