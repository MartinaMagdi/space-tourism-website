<template>
  <div class="home">
    <v-row>
      <v-col cols="12" lg="6" class="animate__animated animate__slideInUp">
        <p class="first">SO, YOU WANT TO TRAVEL TO</p>
        <p class="second s">SPACE</p>
        <p class="third">
          Let’s face it; if you want to go to space, you might as well genuinely
          go to outer space and not hover kind of on the edge of it. Well sit
          back, and relax because we’ll give you a truly out of this world
          experience!
        </p>
      </v-col>
      <v-col cols="12" lg="6" class="right-col animate__animated animate__slideInUp">
        <NuxtLink to="/destination">
          <div class="right-side">EXPLORE</div>
        </NuxtLink>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
};
</script>

<style scoped lang="scss">
@import "../assets/variables";
.home {
  height: 100%;
  padding: 6em 4em;
  .first {
    font-family: "Barlow Condensed", sans-serif;
    font-style: normal;
    font-weight: normal;
    font-size: 1.7em;
    line-height: 34px;
    letter-spacing: 4.725px;
    color: $second-color;
  }

  .second {
    font-family: "Bellefair", serif;
    font-style: normal;
    font-weight: normal;
    font-size: 9.4em;
    line-height: 172px;
  }

  .third {
    font-family: "Barlow", sans-serif;
    font-style: normal;
    font-weight: normal;
    font-size: 1.1em;
    line-height: 32px;
    color: $second-color;
  }

  .right-col {
    display: block;
    margin: auto;
    a {
      text-decoration: unset;
    }
    .right-side {
      font-family: "Bellefair", serif;
      font-size: 2em;
      line-height: 37px;
      letter-spacing: 2px;
      color: $first-color;
      background-color: $third-color;
      text-align: center;
      width: fit-content;
      padding: 2.7em 1em;
      border-radius: 50%;
      margin: auto;
      cursor: pointer;
      box-shadow: 0;
      transition: box-shadow 0.5s ease-out;
      &:hover {
        box-shadow: 0 0 0 50px #ffffff2e;
      }
    }
  }
}

@media (min-width: $mobiles) and (max-width: $tablets) {
  /* Mobiles */
  .home{
    padding: 2em;
    .first, .second, .third{
      text-align: center;
    }
    .second{
      font-size: 6em;
    }
  }
}
@media (min-width: $tablets) and (max-width: $laptops) {
  /* tablet, landscape iPad, lo-res laptops ands desktops */
  .home{
    .first, .second, .third{
      text-align: center;
    }
    .third{
      padding: 0px 11em;
    }
  }
}
</style>