<template>
  <section class="CreerUneSortie_main_container">
    <div class="CreerUneSortie_container_choix">
      <h1 class="CreerUneSortie_title">CR&Eacute;ER UNE SORTIE</h1>
      <div class="CreerUneSortie_liste_CTA_disciplines">
        <div @click="showModaleSport =! showModaleSport" class="CTA_disciplines_container_running">
          <img src="@/assets/pictos/picto_running.png" alt="picto_canoë" />
        </div>
        <div @click="showModaleSport =! showModaleSport"  class="CTA_disciplines_container_velo">
          <img src="@/assets/pictos/picto_velo.png" alt="picto_canoë" />
        </div>
        <div @click="showModaleSport =! showModaleSport"  class="CTA_disciplines_container_canoë">
          <img src="@/assets/pictos/picto_canoë.png" alt="picto_canoë" />
        </div>
      </div>
    </div>

          <!-- CONFIRMATION ENREGISTREMENT -->
      <div  v-show="showMessageEnregistré" class="div_messsage_confirmation_enregistrement">
        <p>Votre sortie a bien été enregistrée</p>
        <p class="croix" @click="showMessageEnregistré = false">X</p>
      </div>

    <!-- MODALE CREATION SORTIE -->
    <div  v-show="showModaleSport" class="ModaleMesSorties_content" >
      <div class="ModaleMesSorties_sport">
        <label for="Sport">Sport</label>
        <select name="sport" id="listes_sports">
          <option value="">Vélo</option>
          <option value="">Running</option>
          <option value="">Canoë</option>
        </select>
      </div>
      <div class="ModaleMesSorties_lieu">
        <label for="Ville">Ville</label>
        <input name="Ville" type="text" value="" />
      </div>
      <div class="ModaleMesSorties_date">
        <label for="date">Date</label>
        <input name="date" type="date" value="08/09/2021" />
      </div>
      <div class="ModaleMesSorties_distance">
        <label for="distance">Distance (en m)</label>
        <input name="distance" type="number" />
      </div>
      <div class="ModaleMesSorties_temps">
        <label for="temps">Temps</label>
        <input name="temps" type="time" />
      </div>
      <div class="ModaleMesSorties_commentaire">
        <label for="commentaire">Commentaire</label>
        <input name="commentaire" type="textarea" />
      </div>
      <div class="ModaleMesSorties_div_boutton">
        <button @click="showMessageEnregistré =! showMessageEnregistré, showModaleSport = false " class="button modifier">Enregistrer</button>
        <button @click="showModaleSport =! showModaleSport" class=" button supprimer">Annuler</button>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "CreerUneSortie",

  data() {
    return {
      showModaleSport: false,
      showMessageEnregistré:false,
      valueVelo:"Vélo",
      valuerRunning:"Running",
      valueVCanoë:"Canoë",
    };
  },
};
</script>

<style scoped lang="scss">
$orange: #f9bb3d;
$font-size1: 12px;
$font-size1: 18px;
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


  .CreerUneSortie_main_container {
    display: grid;
    justify-content: center;
    align-items: center;
    min-height: 400px;

    .CreerUneSortie_container_choix {
      .CreerUneSortie_title {
        display: grid;
         justify-content: center;
        align-content: center;
        margin: 0px 0px 10px 0px;
        font-family: "OS_exbold";
        font-size: 4em;
        color: $orange;
        text-align: center;
      }
      .CreerUneSortie_liste_CTA_disciplines {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
        justify-content: center;
        align-content: center;
        grid-gap: 90px;
        .CTA_disciplines_container_running {
          display: grid;
          justify-items: center;
          align-items: center;
          background-color: $orange;
          width: 150px;
          height: 150px;
          border-radius: 5px;
          img {
            width: 80px;
          }
        }

        .CTA_disciplines_container_velo {
          display: grid;
          justify-content: center;
          align-items: center;
          background-color: $orange;
        width: 150px;
          height: 150px;
          border-radius: 5px;
          img {
            width: 80px;
          }
        }
        .CTA_disciplines_container_canoë {
          display: grid;
          justify-content: center;
          align-items: center;
          background-color: $orange;
          width: 150px;
          height: 150px;
          border-radius: 5px;
          img {
            width: 80px;
          }
        }
      }
    }
  }

  // MESSAGE ENREGISTREMENT
  .div_messsage_confirmation_enregistrement{
    display: flex;
    margin: 0px;
    flex-direction: row;
    font-family: "OS_medium";
    font-size: 1.5em;
    color: #08880e;
    p{
      margin-right: 10px;
    }
    .croix{
      padding: 0px 10px;
      border: 1px solid #08880e;
      border-radius: 5px;
    }
  }
  // MODALE SORTIE
  .ModaleMesSorties_content {
    width: 100%;
    margin: 10px 0px;
    display: grid;
    grid-gap: 50px;
    justify-content: center;
    align-content: center;
    background-color: white;

    .ModaleMesSorties_sport {
      display: grid;
      padding-right: 5px;
      label {
        font-family: "OS_light";
        color: #f9bb3d;
      }
      select {
        width: 250px;
        font-family: "OS_light";
        color: #626162;
        background: none;
        padding: 5px;
        border: 1px solid lightgray;
        border-radius: 5px;
      }
    }
  }
  .ModaleMesSorties_lieu {
    display: grid;
    label {
      font-family: "OS_light";
      color: #f9bb3d;
    }
    input {
      width: 250px;
      font-family: "OS_light";
      color: #626162;
      background: none;
      padding: 5px;
      border: 1px solid lightgray;
      border-radius: 5px;
    }
  }
  .ModaleMesSorties_date {
    display: grid;
    label {
      font-family: "OS_light";
      color: #f9bb3d;
    }
    input {
       width: 250px;
      font-family: "OS_light";
      color: #626162;
      background: none;
      padding: 5px;
      border: 1px solid lightgray;
      border-radius: 5px;
    }
    font-family: "OS_light";
    color: #626162;
  }
  .ModaleMesSorties_distance {
    display: grid;
    label {
      font-family: "OS_light";
      color: #f9bb3d;
    }
    input {
      width: 250px;
      font-family: "OS_light";
      color: #626162;
      background: none;
      padding: 5px;
      border: 1px solid lightgray;
      border-radius: 5px;
    }
  }
  .ModaleMesSorties_temps {
    display: grid;
    label {
      font-family: "OS_light";
      color: #f9bb3d;
    }
    input {
      width: 250px;
      font-family: "OS_light";
      color: #626162;
      background: none;
      padding: 5px;
      border: 1px solid lightgray;
      border-radius: 5px;
    }
  }
  .ModaleMesSorties_commentaire {
    display: grid;
    grid-column: 1/3;
    label {
      font-family: "OS_light";
      color: #f9bb3d;
    }
    input {
      min-height: 60px;
      font-family: "OS_light";
      color: #626162;
      background: none;
      padding: 5px;
      border: 1px solid lightgray;
      border-radius: 5px;
    }
  }
  .ModaleMesSorties_div_boutton {
    width: 100%;
    display: grid;
    grid-column: 2;
    justify-items: right;
    .button {
       width: 150px;
      height: 40px;
      padding: 5px 7px;
      color: white;
      font-family: "OS_medium";
      font-size: 1em;
      border: none;
      border-radius: 5px;
      justify-content: center;
      align-items: center;
    }
    .modifier {
     margin: 0px;
      background: #7eb108;
      display: grid;
      grid-row: 1;
      margin-right: 5px;
    }
    .supprimer {
       margin: 0px;
      display: grid;
      grid-row: 1;
      background-color: #e43e0c;
    }
  }
}



// RESPONSIVE MOBILE

@media screen and (max-width: 500px) {


  .CreerUneSortie_main_container {
    display: grid;
    justify-content: center;
    align-content: center;

    .CreerUneSortie_container_choix {
      .CreerUneSortie_title {
        margin: 0px 0px 10px 0px;
        font-family: "OS_exbold";
        font-size: 2em;
        color: $orange;
        text-align: center;
      }
      .CreerUneSortie_liste_CTA_disciplines {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
        justify-content: center;
        align-content: center;
        grid-gap: 30px;
        .CTA_disciplines_container_running {
          display: grid;
          justify-content: center;
          align-items: center;
          background-color: $orange;
          width: 70px;
          height: 70px;
          border-radius: 5px;
          img {
            width: 30px;
          }
        }

        .CTA_disciplines_container_velo {
          display: grid;
          justify-content: center;
          align-items: center;
          background-color: $orange;
          width: 70px;
          height: 70px;
          border-radius: 5px;
          img {
            width: 30px;
          }
        }
        .CTA_disciplines_container_canoë {
          display: grid;
          justify-content: center;
          align-items: center;
          background-color: $orange;
          width: 70px;
          height: 70px;
          border-radius: 5px;
          img {
            width: 30px;
          }
        }
      }
    }
  }

  // MESSAGE ENREGISTREMENT
  .div_messsage_confirmation_enregistrement{
    display: flex;
    flex-direction: row;
    font-family: "OS_medium";
    color: #08880e;
    p{
      margin-right: 10px;
    }
    .croix{
      padding: 0px 5px;
      border: 1px solid #08880e;
    }
  }
  // MODALE SORTIE
  .ModaleMesSorties_content {
    width: 100%;
    margin: 10px 0px;
    display: grid;
    grid-gap: 10px;
    justify-content: center;
    align-content: center;
    background-color: white;

    .ModaleMesSorties_sport {
      display: grid;
      padding-right: 5px;
      label {
        font-family: "OS_light";
        color: #f9bb3d;
      }
      select {
        width: 130px;
        font-family: "OS_light";
        color: #626162;
        background: none;
        padding: 5px;
        border: 1px solid lightgray;
        border-radius: 5px;
      }
    }
  }
  .ModaleMesSorties_lieu {
    display: grid;
    label {
      font-family: "OS_light";
      color: #f9bb3d;
    }
    input {
      width: 130px;
      font-family: "OS_light";
      color: #626162;
      background: none;
      padding: 5px;
      border: 1px solid lightgray;
      border-radius: 5px;
    }
  }
  .ModaleMesSorties_date {
    display: grid;
    label {
      font-family: "OS_light";
      color: #f9bb3d;
    }
    input {
      width: 130px;
      font-family: "OS_light";
      color: #626162;
      background: none;
      padding: 5px;
      border: 1px solid lightgray;
      border-radius: 5px;
    }
    font-family: "OS_light";
    color: #626162;
  }
  .ModaleMesSorties_distance {
    display: grid;
    label {
      font-family: "OS_light";
      color: #f9bb3d;
    }
    input {
      width: 130px;
      font-family: "OS_light";
      color: #626162;
      background: none;
      padding: 5px;
      border: 1px solid lightgray;
      border-radius: 5px;
    }
  }
  .ModaleMesSorties_temps {
    display: grid;
    label {
      font-family: "OS_light";
      color: #f9bb3d;
    }
    input {
      width: 130px;
      font-family: "OS_light";
      color: #626162;
      background: none;
      padding: 5px;
      border: 1px solid lightgray;
      border-radius: 5px;
    }
  }
  .ModaleMesSorties_commentaire {
    display: grid;
    grid-column: 1/3;
    label {
      font-family: "OS_light";
      color: #f9bb3d;
    }
    input {
      min-height: 40px;
      font-family: "OS_light";
      color: #626162;
      background: none;
      padding: 5px;
      border: 1px solid lightgray;
      border-radius: 5px;
    }
  }
  .ModaleMesSorties_div_boutton {
    width: 100%;
    display: grid;
    grid-column: 2;
    justify-items: right;
    .button {
      padding: 5px 7px;

      color: white;
      font-family: "OS_medium";
      border: none;
      border-radius: 5px;
    }
    .modifier {
      background: #7eb108;
      display: grid;
      grid-row: 1;
      margin-right: 5px;
    }
    .supprimer {
      display: grid;
      grid-row: 1;
      background-color: #e43e0c;
    }
  }
}
</style>
