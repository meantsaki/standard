<template>
  <v-app>
    <home-header/>
    <nuxt />
  </v-app>
</template>

<script>
import HomeHeader from '../components/HomeHeader.vue'
export default {
  components: { HomeHeader },
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js'
    }
  }
}
</script>

<style>
*{
  font-family: 'Montserrat'!important;
}

:root{
  --white:#ffffff;
  --white-darke-1:#FEFEFE00;
  --white-darke-2:#F8F8F8;
  --grey:#CFCFCF;
  --grey-darken-1:#9F9F9F;
  --grey-darken-2:#858585;
  --grey-darken-2:#00000066;
  --green:#B4FF00;
  --dark:#000000;
  --blue:#4B00FF;
}
</style>