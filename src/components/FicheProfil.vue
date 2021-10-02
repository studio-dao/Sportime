<template>
  <div class="Inscription_main_container">
    <div class="Inscription_container">
      <!-- BLOCK LOGO -->
      <div class="Inscription_div_logo">
        <img src="@/assets/logos/logo.png" alt="Logotype" />
        <p class="Inscription_baseline_logo">PROFIL</p>
      </div>

      <!-- BLOCK FORMULAIRE -->
      <div class="Inscription_block_formulaire">
        <div class="Inscription_div_input">
          <label for="">Nom :</label>
          <input type="text" required />
        </div>
        <div class="Inscription_div_input">
          <label for="">Prénom :</label>
          <input type="text" required />
        </div>
        <div class="Inscription_div_input">
          <label for="">Âge :</label>
          <input type="number" required />
        </div>
        <div class="Inscription_div_input">
          <label for="">Téléphone :</label>
          <input type="number" required />
        </div>
        <div class="Inscription_div_input">
          <label for="">E-mail :</label>
          <input type="email" required />
        </div>
      </div>

      <!-- BLOCK BUTTON -->
      <div class="Inscription_div_bouton_enr">
        <router-link to="/Home"
          ><button class="modifier">Modifier</button></router-link
        >
        <router-link to="/Home"
          ><button class="supprimer">Supprimer</button></router-link
        >
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Comp_Inscription",

  data() {
    return {
      alertmdp: false,
      alertRemplir: false,
    };
  },

  methods: {},

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
@media screen and (min-width: 500px) {
  .Header_profil_lien {
    display: none;
  }

  .Inscription_main_container {
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

    .Inscription_container {
      display: grid;
      justify-items: center;
      align-items: center;
      padding: 20px 0px;
      background-color: rgba(255, 255, 255, 0.3);
      border-radius: 15px;

      .Inscription_div_logo {
        display: grid;
        justify-items: center;
        align-items: center;
        img {
          width: 100%;
        }
        .Inscription_baseline_logo {
          color: white;
          font-family: "OS_exbold";
          font-size: 2em;
          margin: 0px;
          justify-self: right;
        }
      }
      .Inscription_block_formulaire {
        .Inscription_div_input {
          display: grid;
          padding: 20px 0px;
          align-items: center;
          width: 100%;
          grid-template-columns: 1.5fr 5fr;
          border-bottom: 1px solid rgba(117, 116, 116, 0.3);

          label {
            font-family: "OS_medium";
            font-size: 20px;
            padding: 0px 10px;
            color: $orange;
            display: grid;
            justify-items: left;
            text-align: left;
            align-items: center;
          }
          input {
            display: grid;
            justify-items: left;
            width: 80%;
            margin: 0px;
            background: white;
            opacity: 0.2;
            border: none;
            height: 20px;
          }
        }
      }
      .Inscription_div_bouton_enr {
        display: grid;
        grid-template-columns: 1fr 1fr;
        margin-top: 20px;

        a {
          display: grid;
          margin: 0px;
          padding: 0px;
          text-decoration: none;

          button {
            padding: 5px 10px;
            height: auto;
            border-radius: 10px;
            border: none;
            color: white;
            font-family: "OS_semiBold";
            font-size: 1em;
            text-align: center;
          }
          .modifier {
            background-color: rgb(21, 122, 7);
          }
          .supprimer {
            background-color: rgb(192, 9, 9);
          }
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
}

// RESPONSIVE MOBILE

@media screen and (max-width: 500px) {
  .Inscription_main_container {
    width: 100vw;
    height: 100vh;
    margin: 0px;
    padding: 10%;
    display: Flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    align-content: center;
    background-image: url("~@/assets/images/mobile_girl_running.jpg");
    background-size: cover;

    .Inscription_container {
      display: grid;
      justify-items: center;
      align-items: center;
      padding: 20px 0px;
      background-color: rgba(255, 255, 255, 0.3);
      border-radius: 15px;

      .Inscription_div_logo {
        width: 80%;
        display: grid;
        justify-items: center;
        align-items: center;
        img {
          width: 100%;
        }
        .Inscription_baseline_logo {
          color: white;
          font-family: "OS_exbold";
          font-size: 1em;
          margin: 0px;
          justify-self: right;
        }
      }
      .Inscription_block_formulaire {
        width: 100%;
        .Inscription_div_input {
          display: grid;
          padding: 20px 0px;
          align-items: center;
          width: 100%;
          grid-template-columns: 2.5fr 5fr;
          border-bottom: 1px solid rgba(117, 116, 116, 0.3);

          label {
            font-family: "OS_semiBold";
            font-size: 14px;
            padding: 0px 10px;
            color: $orange;
            display: grid;
            justify-items: left;
            text-align: left;
            align-items: center;
          }
          input {
            display: grid;
            justify-items: left;
            width: 90%;
            margin: 0px;
            background: white;
            opacity: 0.2;
            border: none;
            height: 20px;
          }
        }
      }
      .Inscription_div_bouton_enr {
        display: grid;
        margin-top: 20px;
        grid-template-columns: 1fr 1fr;

        a {
          display: grid;
          width: 20%;
          margin: 0px;
          padding: 0px;
          text-decoration: none;

          button {
            padding: 5px 10px;
            height: auto;
            border-radius: 10px;
            border: none;
            color: white;
            font-family: "OS_semiBold";
            font-size: 1em;
            text-align: center;
          }
          .modifier {
            background-color: rgb(21, 122, 7);
          }
          .supprimer {
            background-color: rgb(192, 9, 9);
          }
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
}
</style>
