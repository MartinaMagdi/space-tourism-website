<template>
  <div class="destination">
    <v-row class="main-row">
      <p class="title animate__animated animate__shakeX">
        <span>01</span> Pick your destination
      </p>
      <div class="tabs">
        <v-row>
          <v-col cols="12" lg="6"></v-col>
          <v-col class="animate__animated animate__fadeIn" cols="12" lg="6">
            <v-toolbar>
              <template v-slot:extension>
                <v-tabs color="white" v-model="tab" align-with-title>
                  <v-tabs-slider color="white"></v-tabs-slider>

                  <v-tab v-for="item in destination" :key="item.id">
                    {{ item.name }}
                  </v-tab>
                </v-tabs>
              </template>
            </v-toolbar>
          </v-col>
        </v-row>

        <v-tabs-items v-model="tab" class="animate__animated animate__fadeIn">
          <v-tab-item v-for="item in destination" :key="item.id">
            <v-card flat>
              <v-row class="content-row" no-gutters dense>
                <v-col ols="12" lg="6" class="img-container">
                  <img
                    class="tab-img"
                    :src="
                      require(`~/assets/images/destination/${item.images.png}`)
                    "
                  />
                </v-col>
                <v-col cols="12" lg="6" class="second-col">
                  <p class="content-title">{{ item.name }}</p>
                  <p class="des">{{ item.description }}</p>
                  <hr class="hr" />
                  <v-row class="sub-row" no-gutters dense>
                    <v-col cols="12" md="6">
                      <p class="sub-title">AVG. DISTANCE</p>
                      <p class="sub-content">{{ item.distance }}</p>
                    </v-col>
                    <v-col cols="12" md="6">
                      <p class="sub-title">Est. travel time</p>
                      <p class="sub-content">{{ item.travel }}</p>
                    </v-col>
                  </v-row>
                </v-col>
              </v-row>
            </v-card>
          </v-tab-item>
        </v-tabs-items>
      </div>
    </v-row>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tab: null,
      destination: [
        {
          id: 0,
          name: "MOON",
          images: {
            png: "image-moon.png",
            webp: "image-moon.webp",
          },
          description:
            "See our planet as you’ve never seen it before. A perfect relaxing trip away to help regain perspective and come back refreshed. While you’re there, take in some history by visiting the Luna 2 and Apollo 11 landing sites.",
          distance: "384,400 km",
          travel: "3 days",
        },
        {
          id: 1,
          name: "MARS",
          images: {
            png: "image-mars.png",
            webp: "image-mars.webp",
          },
          description:
            "Don’t forget to pack your hiking boots. You’ll need them to tackle Olympus Mons, the tallest planetary mountain in our solar system. It’s two and a half times the size of Everest!",
          distance: "225 mil. km",
          travel: "9 months",
        },
        {
          id: 2,
          name: "EUROPA",
          images: {
            png: "image-europa.png",
            webp: "image-europa.webp",
          },
          description:
            "The smallest of the four Galilean moons orbiting Jupiter, Europa is a winter lover’s dream. With an icy surface, it’s perfect for a bit of ice skating, curling, hockey, or simple relaxation in your snug wintery cabin.",
          distance: "628 mil. km",
          travel: "3 years",
        },
        {
          id: 3,
          name: "TITAN",
          images: {
            png: "image-titan.png",
            webp: "image-titan.webp",
          },
          description:
            "The only moon known to have a dense atmosphere other than Earth, Titan is a home away from home (just a few hundred degrees colder!). As a bonus, you get striking views of the Rings of Saturn.",
          distance: "1.6 bil. km",
          travel: "7 years",
        },
      ],
    };
  },
};
</script>

<style scoped lang="scss">
@import "../assets/variables";
.destination {
  height: 100%;
  padding: 3em 4em 1em 4em;

  .title {
    font-family: "Barlow Condensed", sans-serif !important;
    font-size: 2em !important;
    line-height: 34px;
    letter-spacing: 4.725px;
    text-transform: uppercase;
    span {
      mix-blend-mode: normal;
      opacity: 0.25;
      margin-right: 0.5em;
    }
  }
  .content-row {
    margin-top: 1em;
  }
  .des {
    font-size: 18px;
    line-height: 32px;
    font-family: "Barlow", sans-serif;
    color: $second-color;
  }
  .content-title {
    font-size: 7em !important;
    line-height: 115px;
    font-family: "Bellefair", serif !important;
    color: $third-color;
  }
  .second-col {
    padding-right: 12em;
  }
  .hr {
    background-color: $first-color;
    opacity: 60%;
    margin: 3em 0px 2em 0px;
  }

  .sub-row {
    .sub-title {
      font-family: "Barlow Condensed", sans-serif;
      color: $second-color;
      line-height: 17px;
      letter-spacing: 2.3625px;
      text-transform: uppercase;
    }
    .sub-content {
      color: $third-color;
      line-height: 32px;
      text-transform: uppercase;
      font-family: "Bellefair", serif;
      font-size: 1.5em;
    }
  }
}
@media (min-width: 320px) and (max-width: 961px) {
  /* Mobiles */
  .destination {
    padding: 2em;
    .title {
      font-size: 1.7em !important;
    }
    .content-title {
      font-size: 5em !important;
    }
    .second-col {
      padding-right: 0;
      text-align: center;
    }
    .tabs {
      width: 100%;
    }
    .img-container {
      text-align: center;
      .tab-img {
        width: 12em;
      }
    }
  }
}
</style>

<style lang="scss">
.destination {
  .tabs {
    header {
      background-color: unset !important;
      height: unset !important;
      box-shadow: unset !important;
      .v-tabs-slider-wrapper {
        left: 0;
      }
      .v-toolbar__extension {
        color: white;
      }
      .v-tab {
        color: $second-color !important;
        margin: 0 !important;
      }
      .v-tab--active {
        color: $third-color !important;
      }
    }
    .v-toolbar__content {
      display: none;
    }
  }
  .v-item-group {
    background-color: unset !important;
    .v-card {
      background-color: unset !important;
    }
  }

  @media (min-width: 961px) and (max-width: 1281px) {
    /* tablet, landscape iPad, lo-res laptops ands desktops */
    .main-row {
      text-align: center;
      .title {
        width: 100%;
      }
      .second-col {
        padding: 0 3em;
      }
    }
  }
}

@media (min-width: 320px) and (max-width: 961px) {
  /* Mobiles */
  .app {
    background-image: url("../assets/images/destination/background-destination-mobile.jpg") !important;
  }
  .v-slide-group__prev {
    display: none !important;
  }
  .v-slide-group__content {
    justify-content: center !important;
  }
  .v-tabs-slider-wrapper {
    left: 11.5 !important;
  }
}

@media (min-width: 961px) and (max-width: 1281px) {
  /* tablet, landscape iPad, lo-res laptops ands desktops */
  .app {
    background-image: url("../assets/images/destination/background-destination-tablet.jpg") !important;
  }
  .v-slide-group__content {
    justify-content: center !important;
  }
  .v-tabs-slider-wrapper {
    left: 11.5 !important;
  }
  .title {
    text-align: left;
  }
}

@media (min-width: 1281px) {
  /* hi-res laptops and desktops */
  .app {
    background-image: url("../assets/images/destination/background-destination-desktop.jpg") !important;
  }
  .v-tab {
    &:hover {
      border-bottom: 0.2em solid $second-color;
    }
  }
}
</style>
