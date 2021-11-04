<template>
  <v-app dark>
    <v-main>
      <ShittySeagullz/>
    </v-main>
  </v-app>
</template>

<script>
import ShittySeagullz from './components/ShittySeagullz';

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
#app {
  background: url('./assets/bgimg7.png') no-repeat center!important;
  background-size: cover;
}
</style>
