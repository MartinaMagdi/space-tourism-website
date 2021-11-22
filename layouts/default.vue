<template>
  <v-app class="app">
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

@media (min-width:320px) and (max-width: 961px)  { /* Mobiles */ 
  .app{
    background-image: url('../static/shared/background/background-home-mobile.jpg') !important;
    
  }
}

@media (min-width:961px) and (max-width: 1281px)  { /* tablet, landscape iPad, lo-res laptops ands desktops */ 
  .app{
    background-image: url('../static/shared/background/background-home-tablet.jpg') !important;
  }
}

@media (min-width:1281px) { /* hi-res laptops and desktops */ 
  .app{
    background-image: url('../static/shared/background/background-home-desktop.jpg') !important;
  }
}


</style>
