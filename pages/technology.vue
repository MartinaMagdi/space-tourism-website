<template>
  <div class="technology">
    <p class="title animate__animated animate__shakeX">
      <span>03</span> SPACE LAUNCH 101
    </p>
    <v-carousel hide-delimiter-background height="auto">
      <v-carousel-item class="slider" v-for="item in technology" :key="item.id">
        <v-row>
          <v-col
            cols="12"
            lg="6"
            order-lg="last"
            class="img-col animate__animated animate__fadeIn"
          >
            <img
              class="image-content"
              :alt="item.images.alt"
              :src="
                require(`~/assets/images/technology/${item.images.landscape}`)
              "
            />
          </v-col>
          <v-col
            class="text-col animate__animated animate__fadeIn"
            cols="12"
            lg="6"
            order-lg="first"
          >
            <p class="first">THE TERMINOLOGY…</p>
            <p class="second">{{ item.name }}</p>
            <p class="third">{{ item.description }}</p>
          </v-col>
        </v-row>
      </v-carousel-item>
    </v-carousel>
  </div>
</template>

<script>
import technologyDesktop from "../assets/images/technology/background-technology-desktop.jpg";
import technologyTablet from "../assets/images/technology/background-technology-tablet.jpg";
import technologyMobile from "../assets/images/technology/background-technology-mobile.jpg";

export default {
  data() {
    return {
      technology: [
        {
          id: 0,
          name: "Launch vehicle",
          images: {
            portrait: "image-launch-vehicle-portrait.jpg",
            landscape: "image-launch-vehicle-landscape.jpg",
            alt: "image-launch-vehicle-landscape"
          },
          description:
            "A launch vehicle or carrier rocket is a rocket-propelled vehicle used to carry a payload from Earth's surface to space, usually to Earth orbit or beyond. Our WEB-X carrier rocket is the most powerful in operation. Standing 150 metres tall, it's quite an awe-inspiring sight on the launch pad!",
        },
        {
          id: 1,
          name: "Spaceport",
          images: {
            portrait: "image-spaceport-portrait.jpg",
            landscape: "image-spaceport-landscape.jpg",
            alt: "image-spaceport-landscape"
          },
          description:
            "A spaceport or cosmodrome is a site for launching (or receiving) spacecraft, by analogy to the seaport for ships or airport for aircraft. Based in the famous Cape Canaveral, our spaceport is ideally situated to take advantage of the Earth’s rotation for launch.",
        },
        {
          id: 2,
          name: "Space capsule",
          images: {
            portrait: "image-space-capsule-portrait.jpg",
            landscape: "image-space-capsule-landscape.jpg",
            alt: "image-space-capsule-landscape"
          },
          description:
            "A space capsule is an often-crewed spacecraft that uses a blunt-body reentry capsule to reenter the Earth's atmosphere without wings. Our capsule is where you'll spend your time during the flight. It includes a space gym, cinema, and plenty of other activities to keep you entertained.",
        },
      ],
    };
  },
  mounted() {
    if(this.$device.isDesktop){
      document.getElementById("app").style.backgroundImage = `url(${technologyDesktop})`
    } else if(this.$device.isTablet) {
      document.getElementById("app").style.backgroundImage = `url(${technologyTablet})`
    } else {
      document.getElementById("app").style.backgroundImage = `url(${technologyMobile})`
    }
  },
};
</script>

<style scoped lang="scss">
@import "../assets/variables";

.technology {
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
        font-family: "Barlow Condensed", sans-serif;
        font-size: 1em;
        line-height: 19px;
        letter-spacing: 2.7px;
        text-transform: uppercase;
        color: $second-color;
        mix-blend-mode: normal;
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
  .technology {
    .slider {
      padding-bottom: 5em;
      margin: 4em 0;
    }
  }
}

@media (min-width: 320px) and (max-width: 961px) {
  /* Mobiles */
  .technology {
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
  .technology {
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
    .third {
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
</style>

