<template>
  <v-app id="app" class="app">
    <Header/>
    <Nuxt/>
  </v-app>
</template>

<script>
export default {
  data () {
    return {}
  }
}
</script>
<style lang="scss">
@import '../assets/variables';

::-moz-selection { /* Code for Firefox */
  background: $second-color;
  color: $first-color;
}

::selection {
  background: $second-color;
  color: $first-color;
}

.app{
  background-repeat:no-repeat !important;
  background-position:center center !important;
  background-size: cover !important;
  color: $third-color !important;
}
</style>
