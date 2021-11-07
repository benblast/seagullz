<template>
  <div>
    <v-card>
      <v-card-title>
        WASSUP
      </v-card-title>
      <v-card-text>
        Mah main man
      </v-card-text>
    </v-card>
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
