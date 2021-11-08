<template>
  <div class="mainWrapper">
    <div class="coolWrap screen">
      <div class="hotWrap screen">
        <h1>
          wassup mah seagullz
        </h1>
        <p>
          all good?
        </p>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  name: 'SecondSection',

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
.coolWrap {
  background: url('../assets/secondCard/docks.png') no-repeat bottom right!important;
  background-size: cover;
}
.hotWrap {
  background: url('../assets/secondCard/rm_silhouette.png') no-repeat top left!important;
  background-size: cover;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  font-family: 'Dokdo', Arial, sans-serif;
  font-size: 4rem;
  letter-spacing: -8px;
  line-height: 4rem;
  -webkit-text-stroke: 1px rebeccapurple;
  text-align: center;
}
.mainWrapper {
  background-color: darkcyan;
}

.screen {
  min-height: 100vh!important;
  min-width: 100% !important;
}

</style>
