<template>
  <section class="PrevMesSorties_content_main_container">
    <div class="PrevMesSorties_container_intermediaire">
      <!-- SORTIES   -->
      <div class="PrevMesSorties_content">
        <!-- TITLE -->
        <p class="PrevMesSorties_content_title">MES SORTIES</p>
        <!-- CARD -->
        <div class="PrevMesSorties_content_card_preview">
          <div class="card_PrevMesSorties_picto_discipline">
            <img src="@/assets/pictos/picto_running.png" alt="picto_running" />
          </div>
          <div class="card_preview_lieu_et_date">
            <p class="card_preview_ville">Caen</p>
            <p class="card_preview_date">08/09/21</p>
          </div>
          <p class="card_preview_distance">8000m</p>
          <p class="card_preview_allure">12km/h</p>
          <div
            id="arrow"
            @click="showSortieModale = !showSortieModale"
            class="card_previewRec_picto_fiche_infos"
          >
            <img
              @click="turnArrow"
              src="@/assets/pictos/picto_fleche.png"
              alt="picto_infos"
            />
          </div>
        </div>
      </div>
      <!-- CONFIRMATION MODIFICATION -->
      <div v-show="alertModifier" class="div_messsage_confirmation_suppression">
        <p>Votre sortie a bien été modifiée</p>
        <p class="croix" @click="alertModifier = false">X</p>
      </div>
      <!-- CONFIRMATION SUPPRESSION -->
      <div
        v-show="alertSupprimer"
        class="div_messsage_confirmation_suppression"
      >
        <p>Votre sortie a bien été supprimée</p>
        <p class="croix" @click="alertSupprimer = false">X</p>
      </div>

      <!-- MODALE SORTIE -->

      <div class="ModaleMesSorties_content" v-show="showSortieModale">
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
          <input name="Ville" type="text" value="Caen" />
        </div>
        <div class="ModaleMesSorties_date">
          <label for="date">Date</label>
          <input name="date" type="date" value="08/09/2021" />
        </div>
        <div class="ModaleMesSorties_distance">
          <label for="distance">Distance (en m)</label>
          <input name="distance" type="number" value="8000" />
        </div>
        <div class="ModaleMesSorties_temps">
          <label for="temps">Temps</label>
          <input name="temps" type="time" />
        </div>
        <div class="ModaleMesSorties_commentaire">
          <label for="commentaire">Commentaire</label>
          <input
            name="comentaire"
            type="textarea"
            value="Parcours difficile avec gros dénivelé"
          />
        </div>
        <div class="ModaleMesSorties_div_boutton">
          <button
            @click="
              (showSortieModale = false),
                (alertModifier = true),
                (alertSupprimer = false)
            "
            class="button modifier"
          >
            Modifier
          </button>
          <button
            @click="
              (showSortieModale = false),
                (alertSupprimer = true),
                (alertModifier = false)
            "
            class=" button supprimer"
          >
            Supprimer
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "SectionMesSorties",

  data() {
    return {
      showSortieModale: false,
      alertSupprimer: false,
      alertModifier: false,
    };
  },

  methods: {
    turnArrow() {
      if (this.showSortieModale == true) {
        const arrow = document.getElementById("arrow");
        arrow.addEventListener("onclick", function(event) {
          event.target.style.cssText = "transform: rotate(45°);";
        });
      }
    },
  },
};
</script>

<style scoped lang="scss">
$orange: #f9bb3d;
$grey: #626162;
$font-size1: 12px;
$font-size2: 27px;
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
  .PrevMesSorties_content_main_container {
    width: 100%;
    display: grid;
    justify-items: center;
    align-items: center;

    .PrevMesSorties_container_intermediaire {
      // PREVIEW CARDS SORTIE
      .PrevMesSorties_content {
        width: 100%;
        display: grid;
        justify-content: center;
        justify-items: center;
        align-items: center;
        align-content: center;

        .PrevMesSorties_content_title {
          font-family: "OS_medium";
          color: white;
          margin: 0px 0px 5px 0px;
          font-family: "OS_Exbold";
          font-size: 4em;
        }
        .PrevMesSorties_content_card_preview {
          width: 80%;
          border: 1px solid white;
          border-radius: 5px;
          display: grid;
          grid-template-columns: 2fr 2fr 3fr 1fr 1fr;
          .card_PrevMesSorties_picto_discipline {
            padding: 20px;
            display: grid;
            justify-content: center;
            align-items: center;
            border-right: 1px solid white;
            img {
              width: 60px;
            }
          }
          .card_preview_lieu_et_date {
            border-right: 1px solid white;

            .card_preview_ville {
              display: grid;
              height: 50%;
              justify-content: center;
              align-items: center;
              margin: 0px;
              font-family: "OS_light";
              font-size: $font-size2;
              color: white;
              border-bottom: 1px solid white;
            }
            .card_preview_date {
              display: grid;
              height: 20px;
              justify-items: center;
              align-items: center;
              margin: 0px;
              font-family: "OS_light";
              font-size: $font-size2;
              color: white;
            }
          }
          .card_preview_distance {
            display: grid;
            justify-content: center;
            align-items: center;
            height: 100%;
            margin: 0px;
            font-family: "OS_light";
            font-size: $font-size2;
            color: white;
            border-right: 1px solid white;
          }
          .card_preview_allure {
            display: grid;
            padding: 0px 5px;
            justify-content: center;
            align-items: center;
            height: 100%;
            margin: 0px;
            font-family: "OS_light";
            font-size: $font-size2;
            color: white;
            border-right: 1px solid white;
          }
          .card_previewRec_picto_fiche_infos {
            padding: 5px;
            display: grid;
            justify-content: center;
            align-items: center;
            img {
              width: 30px;
            }
          }
        }
      }

      // MESSAGE SUPPRESSION
      .div_messsage_confirmation_suppression {
        background: rgba(255, 255, 255, 0.5);
        padding-left: 10px;
        display: flex;
        flex-direction: row;
        font-family: "OS_medium";
        font-size: 20px;
        color: #525251;
        p {
          margin-right: 10px;
        }
        .croix {
          padding: 0px 5px;
          border: 1px solid #525251;
        }
      }
      // MESSAGE MODIFICATION
      .div_messsage_confirmation_modification {
        background: rgba(255, 255, 255, 0.5);
        padding-left: 10px;
        display: flex;
        flex-direction: row;
        font-family: "OS_medium";
        font-size: 20px;
        color: #0e9209;
        p {
          margin-right: 10px;
        }
        .croix {
          padding: 0px 5px;
          border: 1px solid #0e9209;
        }
      }

      // MODALE SORTIE
      .ModaleMesSorties_content {
        width: 100%;
        margin: 0px;
        display: grid;
        grid-gap: 10px;
        justify-content: center;
        align-content: center;
        background-color: white;
        padding: 10px 0px;
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
          width: 550px;
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
  }
}

// RESPONSIVE MOBILE

@media screen and (max-width: 500px) {

  .PrevMesSorties_content_main_container {
    display: grid;
    justify-items: center;
    align-items: center;

    .PrevMesSorties_container_intermediaire {
      // PREVIEW CARDS SORTIE
      .PrevMesSorties_content {
        width: 100%;
        display: grid;
        justify-content: center;
        justify-items: center;
        align-items: center;
        align-content: center;

        .PrevMesSorties_content_title {
          font-family: "OS_medium";
          color: white;
          margin: 0px 0px 5px 0px;
          font-family: "OS_Exbold";
          font-size: 2em;
        }
        .PrevMesSorties_content_card_preview {
          width: 100%;
          border: 1px solid white;
          border-radius: 5px;
          display: grid;
          grid-template-columns: 2fr 2fr 3fr 1fr 1fr;
          .card_PrevMesSorties_picto_discipline {
            padding: 5px;
            display: grid;
            justify-content: center;
            align-items: center;
            border-right: 1px solid white;
            img {
              width: 20px;
            }
          }
          .card_preview_lieu_et_date {
            border-right: 1px solid white;

            .card_preview_ville {
              display: grid;
              height: 20px;
              justify-content: center;
              align-items: center;
              margin: 0px;
              font-family: "OS_light";
              font-size: $font-size1;
              color: white;
              border-bottom: 1px solid white;
            }
            .card_preview_date {
              display: grid;
              height: 20px;
              justify-content: center;
              align-items: center;
              margin: 0px;
              font-family: "OS_light";
              font-size: $font-size1;
              color: white;
            }
          }
          .card_preview_ville {
            display: grid;
            justify-content: center;
            align-items: center;
            height: 100%;
            margin: 0px;
            font-size: $font-size1;
            font-family: "OS_light";
            color: white;
            border-right: 1px solid white;
          }
          .card_preview_distance {
            display: grid;
            justify-content: center;
            align-items: center;
            height: 100%;
            margin: 0px;
            font-family: "OS_light";
            font-size: $font-size1;
            color: white;
            border-right: 1px solid white;
          }
          .card_preview_allure {
            display: grid;
            padding: 0px 5px;
            justify-content: center;
            align-items: center;
            height: 100%;
            margin: 0px;
            font-family: "OS_light";
            font-size: $font-size1;
            color: white;
            border-right: 1px solid white;
          }
          .card_previewRec_picto_fiche_infos {
            padding: 5px;
            display: grid;
            justify-content: center;
            align-items: center;
            border-right: 1px solid white;
            img {
              width: 15px;
            }
          }
        }
      }

      // MESSAGE SUPPRESSION
      .div_messsage_confirmation_suppression {
        background: rgba(255, 255, 255, 0.5);
        padding-left: 10px;
        display: flex;
        flex-direction: row;
        font-family: "OS_medium";
        font-size: 14px;
        color: #525251;
        p {
          margin-right: 10px;
        }
        .croix {
          padding: 0px 5px;
          border: 1px solid #525251;
        }
      }
      // MESSAGE MODIFICATION
      .div_messsage_confirmation_modification {
        background: rgba(255, 255, 255, 0.5);
        padding-left: 10px;
        display: flex;
        flex-direction: row;
        font-family: "OS_medium";
        font-size: 14px;
        color: #0e9209;
        p {
          margin-right: 10px;
        }
        .croix {
          padding: 0px 5px;
          border: 1px solid #0e9209;
        }
      }

      // MODALE SORTIE
      .ModaleMesSorties_content {
        width: 100%;
        margin: 0px;
        display: grid;
        grid-gap: 10px;
        justify-content: center;
        align-content: center;
        background-color: white;
        padding: 10px 0px;
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
          width: 290px;
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
  }
}
</style>
