<template>
  <div style="margin-top: 3rem;">
    <div style="width: 100%; color: deeppink; font-family: 'East Sea Dokdo'; -webkit-text-stroke: 2px purple; font-size: 3rem; background: yellowgreen; display: flex; justify-content: center; align-items: center;">
      <h3>Fuck you.</h3>
    </div>
    <v-parallax
        height="450"
        src="../assets/parallax_side.png"
        style="filter: brightness(95%)"
        class="theParallax"
    ></v-parallax>
    <div style="display: flex; flex-wrap: wrap;display: none;">
      <template v-for="i in 44" style="display: flex; flex-wrap: wrap;">
        <v-img :src="require(`../assets/gullz/${i+1}.png`)" width="150px" :key="i"></v-img>
      </template>
    </div>
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
