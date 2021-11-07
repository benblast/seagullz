<template>
  <div style="display: flex; justify-content: center; align-items: center; height: 100vh;">
    <v-card width="50%" style="padding: 1rem; display: flex; height: 100vh;">
      <div style="width: 50%; padding: 1rem; display: flex;">
        <div style="width:100%;">
          <div v-for="(item, i) in Object.keys(bigMetaFile[ID-1])" :key="i">
            <div style="color: gold; font-weight: bold;">
              {{ item }}
            </div>
            <div v-if="item === 'name'" :style="'font-size: 2rem; color: '+colors[Math.floor(Math.random()*colors.length)]">
              {{ bigMetaFile[ID-1][item] }}
            </div>
            <div v-else-if="item !== 'attributes' && item !== 'name'">
              {{ bigMetaFile[ID-1][item] }}
            </div>
            <div v-else v-for="(item, j) in bigMetaFile[ID-1][item]" :key="j" style="display: flex;">
              <div>
                <div style="font-size: 0.7rem; color: greenyellow;">{{ item.trait_type }}</div>
                <div style="font-size: 1.2rem;">{{ item.value }}</div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div style="width: 50%; padding: 1rem;">
        <v-img :src="require(`../assets/tests/img`+bigMetaFile[ID-1].image)" width="15rem"></v-img>
        <v-btn @click="goBack()">Back</v-btn>
        <v-btn @click="goForward()">Forward</v-btn>
      </div>
    </v-card>
    <div>

    </div>
  </div>
</template>

<script>
const bigMetaFile = require('../assets/tests/json/_metadata.json')
export default {
  name: 'CheckGullz',

  data: () => ({
    ID: 1,
    bigMetaFile: bigMetaFile,
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
