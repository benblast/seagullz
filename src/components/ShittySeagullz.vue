<template>
  <div class="mainWindow">
    <div class="infoContainer">
      <div>
        <h1 class="shadow2 grad1 grad2 logoText logoTop" style="">
          Gullz
        </h1>

        <div style="filter: brightness(95%); display: flex; justify-content: space-evenly; margin: 2rem 0; margin-bottom: -1rem; text-align: center; z-index: 1; position: relative;">
          <div class="circle bgrad2">Provably<br>Radical</div>
          <div class="circle bgrad1">Super<br>Limited</div>
          <div class="circle bgrad3">Completely Useless</div>
        </div>
        <v-card class="infoCard" style="z-index: 0;">
          <p style="margin-top: 1rem;">
            Shitty Seagullz is an annoying collection of bird NFTs - kinda unique collectibles that make a lot of racket on the Ethereum blockchain.
            A yet-to-be-determined amount of Seagullz have been shoddily slapped together from a veritable boatload of combinations - all using a run of the mill randomizer thing.
          </p>

          {{info}}
          <div style="display: flex;">
            <h3 style="color: gold; display: flex; justify-content: center; align-items: center; width: 50%;">
              0/X minted!
            </h3>
            <div style="width:50%; display: flex; flex-direction: column; justify-content: center;">
              <v-text-field id="amountTokens" v-model="mintAmount" style="box-shadow: 5px 5px 15px black; border-radius: 5px; font-family: 'East Sea Dokdo', arial, sans-serif; font-size: 3rem; text-shadow: 3px 3px 3px black!important;" class="centered-input"></v-text-field>
              <v-btn class="button">SOON</v-btn>
            </div>
          </div>
        </v-card>
      </div>
    </div>
  </div>
</template>

<script>
import Web3 from 'web3'

export default {
  name: 'ShittySeagullz',

  data: () => ({
    abi: [{
      "inputs": [
        {
          "internalType": "uint256",
          "name": "amount",
          "type": "uint256"
        }
      ],
      "name": "mint",
      "outputs": [],
      "stateMutability": "payable",
      "type": "function"
    }],
    addr: '',
    info: '',
    mintAmount: 0,
    gullz: [
      {
        img: require('../assets/gullz/1.png')
      }
    ]
  }),
  methods: {
    async mintGull () {
      try {
        const amount = document.getElementById('amountTokens').value
        console.log('härhär', amount)
        const accounts = await window.ethereum.request({ method: 'eth_requestAccounts' })
        this.info = accounts + " connected"

        const web3 = new Web3(window.ethereum)

        const GullzContract = await new web3.eth.Contract(this.abi, this.addr)
        await GullzContract.methods.mint(amount).send({from: window.ethereum.selectedAddress, value: '40000000000000000' })
        console.log('done')
      } catch (e) {
        this.info = e
        console.log('mint fail ffs', e)
      }

    }
  }
}
</script>

<style scoped>

@media (max-width: 1000px) {
  .logoText {
    font-size: 12rem!important;
  }
  .logoTop {
    line-height: 12rem!important;
  }
  .shadow2 {
    -webkit-text-stroke: 1px darkmagenta!important;
  }

  .circle {
    font-size: 2rem!important;
    line-height: 1.5rem!important;
    letter-spacing: -5px;
    height: 6.5rem!important;
    width: 5rem!important;
    text-transform: uppercase;
  }

  .mainWindow {
  }
  .infoContainer {
    width: 100% !important;
    margin: 0 0 1rem 0!important;
    padding: 0!important;
  }
  .infoCard p {
    font-size: 1rem!important;
  }
}

.logoTop {
  z-index: 2;
  position: relative;
  text-align: center;
  line-height: 20rem;
  font-size: 20rem;
}
.mainWindow {
  display: flex;
  justify-content: center;
  width: 100%;
  height: 100vh;
  align-items: center;
}
.infoContainer {
  width: 50%;
  padding: 0 2rem;
  margin-bottom: 1rem;
  display: flex;
  flex-direction: column;
  align-items: center;
}

@font-face {
  font-family: "Grotesk";
  src: local("Grotesk"),
  url(../assets/fonts/hk-grotesk.medium.ttf) format("truetype");
}
body {
  font-family: "Grotesk", Helvetica, sans-serif;
}
.centered-input >>> input {
  text-align: center
}
h3 {
  font-family: "Grotesk", Helvetica, sans-serif;
  font-size: 2rem;
}
h1 {
  font-family: "East Sea Dokdo", Arial, sans-serif;
  line-height: 25.5rem;
  filter: brightness(95%);
}
.shadow {
  filter: drop-shadow(3px 3px rebeccapurple) drop-shadow(2px 2px mediumvioletred) drop-shadow(3px 3px deeppink) drop-shadow(15px 15px 10px black);
  -webkit-text-stroke: 2px darkmagenta;
  -webkit-font-smoothing: antialiased;
}
.shadow2 {
  filter: drop-shadow(3px 3px rebeccapurple) drop-shadow(2px 2px mediumvioletred) drop-shadow(3px 3px deeppink) drop-shadow(15px 15px 10px black);
  -webkit-text-stroke: 2px darkmagenta;
  -webkit-font-smoothing: antialiased;
}
.button {
  background: linear-gradient(180deg, yellow, cyan);
  height: 3rem!important;
  font-size: 2.5rem!important;
  font-family: "East Sea Dokdo", Helvetica, sans-serif;
  color: blueviolet!important;
  box-shadow: 5px 5px 15px black;
}
.circle {
  font-family: "Dokdo", Helvetica, sans-serif;
  font-size: 3.5rem;
  line-height: 2rem;
  letter-spacing: -5px;
  word-break: keep-all;
  text-shadow: 5px 5px 10px black;
  -webkit-text-stroke: 0.8px black;
  box-shadow: 5px 5px 25px #111111;
  height: 9rem;
  width: 7rem;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.infoCard {
  backdrop-filter: blur(10px) !important;
  background-color: rgba(255, 255, 255, 0.2) !important;
  box-shadow: 0 0 35px black !important;
  border: 12px solid blueviolet!important;
  border-radius: 25px!important;
  padding: 1rem 2rem;
  text-shadow: 3px 3px 3px black;
}
.metal {
  background: linear-gradient(
      hsl(239, 50%, 30%) 15%,
      hsl(239, 50%, 40%) 25%,
      hsl(200, 60%, 50%) 35%,
      hsl(100, 70%, 80%) 45%,
      hsl(60, 100%, 98%) 50%,
      hsl(240, 0%, 0%) 52%,
      hsl(240, 10%, 10%) 60%,
      hsl(240, 50%, 30%) 70%,
      hsl(220, 70%, 60%) 80%,
      hsl(212, 92%, 76%) 85%
  );

}
.bgrad1 {
  background: linear-gradient(180deg, cyan, deeppink);
}
.bgrad2 {
  background: linear-gradient(180deg, magenta, yellow);
}
.bgrad3 {
  background: linear-gradient(180deg, mediumpurple, chartreuse);
}
.grad1 {
  background: linear-gradient(180deg, magenta, yellow);
  background-clip: text;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -moz-text-fill-color: transparent;
  -webkit-text-fill-color: transparent;
}
.grad2 {
  background: linear-gradient(180deg, yellow, cyan);
  background-clip: text;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -moz-text-fill-color: transparent;
  -webkit-text-fill-color: transparent;
}
p {
  font-family: 'Grotesk', Helvetica, sans-serif;
  font-size: 1.3rem;
}
.theGrid {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-template-rows: 1fr 1fr 1fr;
  grid-template-areas: "a b c" "d e f" "g h i";
}
</style>
