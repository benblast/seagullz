<template>
  <v-app class="ass">
    <ShittySeagullz style=""/>
    <MidSection/>
    <SecondSection/>
  </v-app>
</template>

<script>
import ShittySeagullz from "./components/ShittySeagullz"
import MidSection from "./components/MidSection"
import SecondSection from "./components/SecondSection"
export default {
  name: 'App',

  components: {
    ShittySeagullz,
    MidSection,
    SecondSection
  },

  data: () => ({
    //
  }),
};
</script>
<style scoped>
.ass {

  background: url('./assets/bgimg7_filesize3_gullz_narrow.png') no-repeat center!important;
  background-size: cover!important;
  height: 100vh!important;
}

</style>
