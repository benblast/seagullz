<template>
  <div>
    <div style="width: 100%; color: deeppink; font-family: 'Dokdo'; letter-spacing: -5px; -webkit-text-stroke: 2px purple; font-size: 3rem; background: yellowgreen; display: flex; justify-content: center; align-items: center;">
      <h2 style="text-align: center">SEAGULLS ARE COOL</h2>
    </div>
    <v-parallax
        height="450"
        src="../assets/parallax_side.png"
        style="filter: brightness(95%)"
        class="theParallax"
    ></v-parallax>
  </div>
</template>

<script>
export default {
  name: 'MidSection',

  data: () => ({
    ID: 1,
    colors: [
      'greenyellow',
      'magenta',
      'cyan',
      'deeppink',
      'yellow',
      'rebeccapurple'
    ]
  }),
  methods: {
    goForward() {
      if (this.ID > 0) {
        this.ID = this.ID + 1
        console.log(this.ID)
      }
    },
    goBack() {
      if (this.ID > 1) {
        this.ID = this.ID - 1
        console.log(this.ID)
      }
    },
    readJson() {

    }
  }
};
</script>
<style scoped>
.theParallax {
}

</style>
