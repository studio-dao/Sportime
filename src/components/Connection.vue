<template>
  <div class="Connection_main_container">
    <div class="Connection_container_identification">
      <div class="Connection_identification_div_logo">
        <img src="@/assets/logos/logo.png" alt="Logotype" />
      </div>
      <div class="Connection_identification_div_pseudo">
        <label for="">PSEUDO</label>
        <input type="text" required />
      </div>
      <div class="Connection_identification_div_mdp">
        <label for="">MOT DE PASSE</label>
        <input type="password" required />
        <a class="Connection_identification_oubli_lien" href="#"
          ><p
            @click="alertmdp =! alertmdp"
            class="Connection_identification_oubli_parag"
          >
            Mot de passe oublié ?
          </p>
        </a>
        <p id="alertmdp" v-show="alertmdp" class="connection_message_mdp_reinitialise">
          Un mail vous à été envoyé afin de réinitialiser votre mot de passe
        </p>
        <p id="alertRemplir"  v-show="alertRemplir" class="connection_message_remplir_champs">
          Veuillez remplir les champs demandés
        </p>
      </div>
      <router-link to="/Home"><button>ENTRER</button></router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "Connection",
  props: {
    msg: String,
  },
  data() {
    return {
     alertmdp:false,
      alertRemplir:false,
    };
  },

  methods: {

  },

   alertRemplirChamps() {
      alert("Un mail vous a été envoyé pour réinitialiser votre mot de passe.");
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

.Connection_main_container {
  width: 100vw;
  height: 100vh;
  margin: 0px;
  display: Flex;
  flex-direction: column;
  justify-content: center;
  justify-items: center;
  align-items: center;
  align-content: center;
  background-image: url("~@/assets/images/mobile_girl_running.jpg");
  background-size: cover;
  .Connection_container_identification {
    display: grid;
    justify-items: center;
    align-items: center;
    width: 80%;
    height: 80%;
    background-color: rgba(255, 255, 255, 0.3);
    border-radius: 15px;

    .Connection_identification_div_logo {
      display: grid;
      justify-items: center;
      align-items: center;
      img {
        width: 80%;
      }
    }
    .Connection_identification_div_pseudo {
      display: grid;
      width: 80%;
      label {
        font-family: "OS_semiBold";
        color: $orange;
      }
      input {
        background: none;
        border: 1px solid white;
        border-radius: 5px;
        height: 20px;
      }
    }
    .Connection_identification_div_mdp {
      display: grid;
      width: 80%;
      label {
        font-family: "OS_semiBold";
        color: $orange;
      }
      input {
        background: none;
        border: 1px solid white;
        border-radius: 5px;
        height: 20px;
      }
      .Connection_identification_oubli_lien {
        width: 80%;
        text-decoration: none;
        display: grid;
        justify-items: start;
        align-items: start;
        .Connection_identification_oubli_parag {
          margin-top: 10px;
          padding: 0px;
          text-align: left;
          font-size: 14px;
          color: rgb(78, 77, 77);
          font-family: "OS_light";
        }
      }
    }

    a {
      display: grid;
      width: 50%;
      margin: 0px;
      padding: 0px;
      text-decoration: none;
      button {
        padding: 5px 10px;
        height: auto;
        background-color: $orange;
        border-radius: 10px;
        border: none;
        color: white;
        font-family: "OS_semiBold";
        font-size: 1.5em;
        text-align: center;
      }
    }
    .connection_message_mdp_reinitialise {

      font-family: "OS_semiBold";
      font-size: 14px;
      color: rgb(21, 122, 7);
    }
    .connection_message_remplir_champs {

      font-family: "OS_semiBold";
      font-size: 14px;
      color: rgb(192, 9, 9);
    }
  }
}

</style>
