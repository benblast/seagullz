<template>
  <v-app dark class="ass">
    <ShittySeagullz style=""/>
  </v-app>
</template>

<script>
import ShittySeagullz from "./components/ShittySeagullz"

export default {
  name: 'App',

  components: {
    ShittySeagullz,
  },

  data: () => ({
    //
  }),
};
</script>
<style scoped>
.ass {
  background: url('./assets/bgimg7_filesize3_gullz2.png') no-repeat center!important;
  background-size: cover!important;
}

</style>
