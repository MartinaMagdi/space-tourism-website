<template>
  <div class="crew">
    <p class="title animate__animated animate__shakeX"><span>02</span> Meet your crew</p>
    <v-carousel hide-delimiter-background height="auto">
      <v-carousel-item class="slider" v-for="item in crew" :key="item.id">
        <v-row>
          <v-col cols="12" lg="6" order-md="last" order-lg="last" class="img-col animate__animated animate__fadeIn">
            <img
              class="image-content"
              :src="require(`~/assets/images/crew/${item.images.png}`)"
            />
          </v-col>
          <v-col class="text-col animate__animated animate__fadeIn" cols="12" lg="6" order-md="first" order-lg="first">
            <p class="first">{{ item.role }}</p>
            <p class="second">{{ item.name }}</p>
            <p class="third">{{ item.bio }}</p>
          </v-col>
        </v-row>
      </v-carousel-item>
    </v-carousel>
  </div>
</template>

<script>
import crewDesktop from "../assets/images/crew/background-crew-desktop.jpg";
import crewTablet from "../assets/images/crew/background-crew-tablet.jpg";
import crewMobile from "../assets/images/crew/background-crew-mobile.jpg";

export default {
  data() {
    return {
      crew: [
        {
          id: 0,
          name: "Douglas Hurley",
          images: {
            png: "image-douglas-hurley.png",
            webp: "image-douglas-hurley.webp",
          },
          role: "Commander",
          bio: "Douglas Gerald Hurley is an American engineer, former Marine Corps pilot and former NASA astronaut. He launched into space for the third time as commander of Crew Dragon Demo-2.",
        },
        {
          id: 1,
          name: "Mark Shuttleworth",
          images: {
            png: "image-mark-shuttleworth.png",
            webp: "image-mark-shuttleworth.webp",
          },
          role: "Mission Specialist",
          bio: "Mark Richard Shuttleworth is the founder and CEO of Canonical, the company behind the Linux-based Ubuntu operating system. Shuttleworth became the first South African to travel to space as a space tourist.",
        },
        {
          id: 2,
          name: "Victor Glover",
          images: {
            png: "image-victor-glover.png",
            webp: "image-victor-glover.webp",
          },
          role: "Pilot",
          bio: "Pilot on the first operational flight of the SpaceX Crew Dragon to the International Space Station. Glover is a commander in the U.S. Navy where he pilots an F/A-18.He was a crew member of Expedition 64, and served as a station systems flight engineer.",
        },
        {
          id: 3,
          name: "Anousheh Ansari",
          images: {
            png: "image-anousheh-ansari.png",
            webp: "image-anousheh-ansari.webp",
          },
          role: "Flight Engineer",
          bio: "Anousheh Ansari is an Iranian American engineer and co-founder of Prodea Systems. Ansari was the fourth self-funded space tourist, the first self-funded woman to fly to the ISS, and the first Iranian in space.",
        },
      ],
    };
  },
  mounted() {
    if(this.$device.isDesktop){
      document.getElementById("app").style.backgroundImage = `url(${crewDesktop})`
    } else if(this.$device.isTablet) {
      document.getElementById("app").style.backgroundImage = `url(${crewTablet})`
    } else {
      document.getElementById("app").style.backgroundImage = `url(${crewMobile})`
    }
  }
};
</script>

<style scoped lang="scss">
@import "../assets/variables";
.crew {
  height: 100%;
  padding: 3em 4em 0 4em;
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
  .slider {
    .img-col {
      text-align: center;
      .image-content {
        border-bottom: 1px solid #d0d6f961;
      }
    }
    .text-col {
      .first {
        font-family: "Bellefair", serif;
        font-size: 2em;
        line-height: 37px;
        text-transform: uppercase;
        color: $third-color;
        mix-blend-mode: normal;
        opacity: 0.5;
      }

      .second {
        font-family: "Bellefair", serif;
        font-size: 3.5em;
        line-height: 64px;
        text-transform: uppercase;
        color: $third-color;
      }

      .third {
        font-family: "Barlow", sans-serif;
        font-size: 1.1em;
        line-height: 32px;
        color: $second-color;
        text-align: left;
      }
    }
  }
}
@media (min-width: 1281px) {
  /* hi-res laptops and desktops */
  .crew {
    .slider {
      padding-bottom: 5em;
      .text-col {
        display: flex;
        flex-wrap: wrap;
        align-content: center;
      }
    }
  }
}
@media (min-width: 320px) and (max-width: 961px) {
  /* Mobiles */
  .crew {
    padding: 1em 1em 0em 1em;
    text-align: center;
    .title {
      font-size: 1.7em !important;
    }
    .image-content {
      width: 100%;
    }
    .first {
      font-size: 1.5em !important;
    }
    .second {
      font-size: 2em !important;
    }
    .third {
      font-size: 1em !important;
      text-align: center !important;
    }
    .slider {
      padding-bottom: 2em;
    }
  }
}
@media (min-width: 961px) and (max-width: 1281px) {
  /* tablet, landscape iPad, lo-res laptops ands desktops */
  .crew {
    text-align: center;
    padding-bottom: 0;
    .slider {
      margin-top: 3em;
      padding-bottom: 4em;
    }
    .title {
      width: 100%;
      text-align: left;
    }
    .third{
      text-align: center !important;
    }
  }
}
</style>

<style lang="scss">
.v-window__next,
.v-window__prev {
  display: none;
}

.v-btn--icon.v-size--small {
  color: #8b8282;
  mix-blend-mode: normal;
  opacity: 0.17;
}


.v-btn--active{
    color: $third-color !important;
    opacity: unset !important;
    mix-blend-mode: unset !important;
}
</style>
