<template>
  <div style="background-color: darkcyan; min-height: 100vh;">
    <h1>
      wassup mah seagullz
    </h1>
    <p>
      all good?
    </p>
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


</style>
