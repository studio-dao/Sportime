<template>
  <div class="Footer_main_container">
    <footer class="Footer">
      <div class="Footer_logo">
        <img src="@/assets/logos/logo.png" alt="picto_logo" />
      </div>
      <div class="footer_column_contact">
        <ul>
          <a href="mailto: contact@sportime.com">
            <li class="contact">
              contact
            </li>
          </a>
          <li class="adresse">
            <p class="sportime">Sportime</p>
            <p>6 rue de la chapelle 75600 Champs</p>
          </li>
        </ul>
      </div>
      <div class="footer_div_infos">
        <ul>
          <a href="#">
            <li>Mentions Légales</li>
          </a>
          <a href="#">
            <li>
              Facebook
            </li>
          </a>
          <a href="#">
            <li>Instagram</li>
          </a>
        </ul>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: "Footer",

  data() {
    return {};
  },
};
</script>

<style scoped lang="scss">
$orange: #f9bb3d;
@media screen and (min-width: 500px) {
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

  p {
    margin: 0px;
    padding: 0px;
  }

  .Footer_main_container {
    width: 100vw;
    position: relative;
    margin: 0px;
    display: grid;
    bottom: 0px;
    .Footer {
      width: 100%;
      margin: 0px;
      display: grid;
      grid-template-columns: 1fr 1fr 1fr;
      width: 100%;
      background-color: rgba($color: #302f2f, $alpha: 1);
      .Footer_logo {
        display: grid;
        justify-items: center;
        align-items: center;
        font-family: "OS_light";
        font-size: 12px;
        color: rgb(194, 191, 191);
        img {
          width: 70%;
        }
      }
      .footer_column_contact {
        display: grid;
        border-left: 1px solid $orange;
        justify-items: left;
        align-items: center;
        font-family: "OS_light";
        font-size: 12px;
        color: rgb(194, 191, 191);
        ul {
          list-style: none;
          margin: 0px;
          padding: 0px 10px;
          a {
            text-decoration: none;
            color: rgb(194, 191, 191);
            .contact {
              font-size: 20px;
            }
          }
          .adresse {
            margin: 5px 0px;
            font-size: 20px;
            .sportime {
              font-size: 25px;
              font-weight: bold;
            }
          }
        }
      }
      .footer_div_infos {
        display: grid;
        border-left: 1px solid $orange;
        justify-items: left;
        align-items: center;
        font-family: "OS_light";
        font-size: 20px;
        color: rgb(194, 191, 191);
        ul {
          list-style: none;
          margin: 0px;
          padding: 0px 10px;
          a {
            text-decoration: none;
            color: rgb(194, 191, 191);
            li {
              margin: 5px 0px;
            }
          }
        }
      }
    }
  }
}
@media screen and (max-width: 500px) {
  p {
    margin: 0px;
    padding: 0px;
  }

  .Footer_main_container {
    width: 100vw;
    background-color: rgba($color: #302f2f, $alpha: 1);
    .Footer {
      width: 100%;
      margin: 0px;
      display: grid;
      padding: 5px;
      grid-template-columns: repeat(3, 1fr);
      .Footer_logo {
        display: grid;
        justify-items: center;
        align-items: center;
        color: rgb(194, 191, 191);
        img {
          width: 90%;
        }
      }
      .footer_column_contact {
        display: grid;
        border-left: 1px solid $orange;
        justify-items: left;
        align-items: center;
        font-family: "OS_light";
        font-size: 10px;
        color: rgb(194, 191, 191);
        ul {
          list-style: none;
          margin: 0px;
          padding: 0px 10px;
          a {
            text-decoration: none;
            color: rgb(194, 191, 191);
            .contact {
            }
          }
          .adresse {
            margin: 5px 0px;
            font-size: 10px;
            .sportime {
              font-size: 14px;
              font-weight: bold;
            }
          }
        }
      }
      .footer_div_infos {
        display: grid;
        border-left: 1px solid $orange;
        justify-items: left;
        align-items: center;
        font-family: "OS_light";
        font-size: 10px;
        color: rgb(194, 191, 191);
        ul {
          list-style: none;
          margin: 0px;
          padding: 0px 10px;
          a {
            text-decoration: none;
            color: rgb(194, 191, 191);
            li {
              margin: 5px 0px;
            }
          }
        }
      }
    }
  }
}
</style>
