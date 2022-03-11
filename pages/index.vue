<template>
  <div id="app">
    <div class="toads-background">
    <div id="wrapper" style="margin-top:80px">
      <img :src="toad_logo" style="height: 115px; position:sticky; margin-bottom:10px">
      <h1
      id="aniation"
      class="text-glitch glitch"
      data-text="Toad.Network"
      style="color:#8ad98a;letter-spacing: 0.15em; margin-bottom:25px; font-size: calc(30px + 2vw)">
      Toad.Network
      </h1>
      <span
      class="sub"
      style="letter-spacing: 0.5em; color: #bfdbbf; font-weight: 1000; font-size: 1.3rem;">
      Defi Ecosystem
      </span>
    </div>
    <v-row
    justify="center"
    style="margin-top:35px">

      <v-col
      cols="12"
      sm="auto"
      >
        <v-btn
          href="https://dapps.padswap.exchange/swap"
          target="_blank"
          style="width: 100%; border-radius: 12px; background: linear-gradient(128.17deg, rgb(0, 255, 77) -14.78%, rgb(117, 113, 255) 110.05%) 0% 0% repeat scroll rgba(0, 0, 0, 0);"
          >
          <v-icon style="margin-right: 5px">mdi-swap-horizontal</v-icon>
          Swap
        </v-btn>
      </v-col>

      <v-col
      cols="12"
      sm="auto"
      >
        <v-btn
          href="http://dapps.padswap.exchange/"
          target="_blank"
          style="width: 100%; border-radius: 12px; background: linear-gradient(128.17deg, rgb(0, 255, 77) -14.78%, rgb(117, 113, 255) 110.05%) 0% 0% repeat scroll rgba(0, 0, 0, 0);"
          >
          <v-icon style="margin-right: 5px">mdi-sprout</v-icon>
          Stake
        </v-btn>
      </v-col>

      <v-col
      cols="12"
      sm="auto"
      >
        <v-btn
          href="https://docs.toad.network/"
          target="_blank"
          outlined
          style="width:100%; border-radius:12px;"
          >
          Learn more
        </v-btn>
      </v-col>

    </v-row>
    </div>
<!--     <v-row
      style="margin-top:100px; margin-left: 10vw; margin-right: 10vw">
      <v-col
      justify="center"
      cols="12"
      sm="4"
      >
      <div style="font-size:2.5rem !important;" class="stats text-center">11+</div>
      <div class="text-center">Months in development</div>
      </v-col>
      <v-col
      cols="12"
      sm="4"
      >
      <div style="font-size:2.5rem !important;" class="stats text-center">6+</div>
      <div class="text-center">Unique DeFi products</div>
      </v-col>
      <v-col
      cols="12"
      sm="4"
      >
      <div style="font-size:2.5rem !important;" class="stats text-center">7+</div>
      <div class="text-center">Projects launched on PadSwap</div>
      </v-col>
    </v-row> -->

  <!-- Intro section -->
  <!-- Contains the links to dedicated slides for each product -->
  <div class="product-section">
    <!-- Project pitch -->
    <div class="text-center text-h3 second-subtitle">Cross-chain, multi-purpose DeFi network</div>
    <div class="text-center text-h5 second-description">Toad.Network is an evergrowing DeFi ecosystem, offering an all-in-one platform for users and providing advanced solutions for projects.</div>

    <!-- Button row -->
    <v-row class="justify-center title-card-container">
      <v-card
       @click="goto('padswap')"
        class="title-card hover-rgb">
        <div class="icon-container">
          <img src="../static/icon-pad.png">
        </div>
        <div class="title-card-name">PadSwap</div>
        <v-card-subtitle class="text-center" style="font-size: 1.05rem">Exchange tokens on PadSwap.</v-card-subtitle>
      </v-card>

      <v-card
       @click="goto('farms')"
        class="title-card hover-rgb">
        <div class="icon-container">
          <img src="../static/farms.png">
        </div>
        <div class="title-card-name">Farms</div>
        <v-card-subtitle class="text-center" style="font-size: 1.05rem">Earn passive income by staking.</v-card-subtitle>
      </v-card>

      <v-card
       @click="goto('dplp')"
        class="title-card hover-rgb">
        <div class="icon-container">
          <img src="../static/icon-dplp.png">
        </div>
        <div class="title-card-name">DPLP</div>
        <v-card-subtitle class="text-center" style="font-size: 1.05rem">The best way to ensure that a project is eternally liquid.</v-card-subtitle>
      </v-card>

      <v-card
       @click="goto('launchpad')"
        class="title-card hover-rgb">
        <div class="icon-container">
          <img src="../static/rocket.png">
        </div>
        <div class="title-card-name">LaunchPAD</div>
        <v-card-subtitle class="text-center" style="font-size: 1.05rem">Launch your token in a few clicks.<br>No coding knowledge required.</v-card-subtitle>
      </v-card>

      <v-card
       @click="goto('bridge')"
        class="title-card hover-rgb">
        <div class="icon-container">
          <img src="../static/icon-bridge.png">
        </div>
        <div class="title-card-name">Cross-chain bridge</div>
        <v-card-subtitle class="text-center" style="font-size: 1.05rem">Transfer tokens between chains.</v-card-subtitle>
      </v-card>

      <v-card
       @click="goto('auctions')"
        class="title-card hover-rgb">
        <div class="icon-container">
          <img src="../static/auction.png">
        </div>
        <div class="title-card-name">Auctions</div>
        <v-card-subtitle class="text-center" style="font-size: 1.05rem">Donate to the project's liquidity and receive their tokens in return.</v-card-subtitle>
      </v-card>

      <v-card
       @click="goto('vault')"
        class="title-card hover-rgb">
        <div class="icon-container">
          <img src="../static/icon-vault.png">
        </div>
        <div class="title-card-name">Vault</div>
        <v-card-subtitle class="text-center" style="font-size: 1.05rem">Creates real backing for PAD, accumulated from PadSwap fees.</v-card-subtitle>
      </v-card>

      <v-card
       @click="goto('roadmap')"
        class="title-card hover-rgb">
        <div class="icon-container">
          <img src="../static/icon-roadmap.png">
        </div>
        <div class="title-card-name">TOADmap</div>
        <v-card-subtitle class="text-center" style="font-size: 1.05rem">See what we're up to!</v-card-subtitle>
      </v-card>

    </v-row>
  </div>

  <BackToTopButton/>

  <!-- Various product sections -->

  <div ref="padswap">
    <Padswap/>
  </div>

  <div ref="farms">
    <Farms/>
  </div>

  <div ref="dplp">
    <DPLP/>
  </div>

  <div ref="launchpad">
    <LaunchPad/>
  </div>

  <div ref="bridge">
    <Bridge/>
  </div>

  <div ref="auctions">
    <Auctions/>
  </div>

  <div ref="vault">
    <Vault/>
  </div>

  <div ref="roadmap">
    <SectionRoadmap/>
  </div>

  <!-- Partners section -->
  <div class="text-center">
    <div class="section-banner" ref="partners">
      <img src="../static/banners/banner-dao.jpg">
      <div class="banner-border"></div>
      <div class="section-title-text">Our Partners</div>
    </div>
  </div>
  <div>
    <div class="partners">
      <a
      href="https://the-crossing.io/"
      target="_blank">
        <div class="partner-content">
        <img src="../static/partners/catoshi.png">
        <span>Catoshi Bridge</span>
        </div>
      </a>
      <a
      href="https://coinmarketcap.com/currencies/toad-network/"
      target="_blank">
        <div class="partner-content">
        <img src="../static/partners/cmc.png">
        <span>CoinMarketCap</span>
        </div>
      </a>
      <a
      href="https://defillama.com/protocol/padswap"
      target="_blank">
        <div class="partner-content">
        <img src="../static/partners/defi-llama.png">
        <span>Defi Llama</span>
        </div>
      </a>
      <a
      href="https://blockfolio.com/"
      target="_blank">
        <div class="partner-content">
        <img src="../static/partners/ftx.png">
        <span>FTX (Blockfolio)</span>
        </div>
      </a>
      <a
      href="https://bubbles.moonlighttoken.com/token/0x463e737d8f740395abf44f7aac2d9531d8d539e9"
      target="_blank">
        <div class="partner-content">
        <img src="../static/partners/moonlight.png">
        <span>Bubble Maps</span>
        </div>
      </a>
      <a
      href="https://spadetech.io/wp-content/uploads/2021/06/toad_Padswap_audit_report.pdf"
      target="_blank">
        <div class="partner-content">
        <img src="../static/partners/spade.png">
        <span>Spade Audits</span>
        </div>
      </a>
      <a
      href="https://www.xt.com/trade/toad_usdt"
      target="_blank">
        <div class="partner-content">
        <img src="../static/partners/xt.png">
        <span>XT.com</span>
        </div>
      </a>
      <a
      href="https://poocoin.app/tokens/0x463e737d8f740395abf44f7aac2d9531d8d539e9"
      target="_blank">
        <div class="partner-content">
        <img src="../static/partners/poocoin.png">
        <span>Poocoin</span>
        </div>
      </a>
      <a
      href="https://piramyd.me/toad-network-x-piramyd/"
      target="_blank">
        <div class="partner-content">
        <img src="../static/partners/piramyd.png">
        <span>Piramyd Store</span>
        </div>
      </a>
      <a
      href="https://tokensniffer.com/"
      target="_blank">
        <div class="partner-content">
        <img src="../static/partners/tokensniffer.png">
        <span>Token Sniffer</span>
        </div>
      </a>
      <a
      href="https://dexscreener.com/moonriver/padswap"
      target="_blank">
        <div class="partner-content">
        <img src="../static/partners/dexscreener.png">
        <span>DEX Screener</span>
        </div>
      </a>
      <a
      href="https://3commas.io/d/apps/69"
      target="_blank">
        <div class="partner-content">
        <img src="../static/partners/3Commas.png">
        <span>3Commas</span>
        </div>
      </a>
    </div>
  </div>
</div>

</template>
<script>
export default {
  layout: 'landing',
  data () {
    return {
      toad_logo: ''
    }
  },
  components: {
  },
  mounted () {
    this.getRandomToad()
    setTimeout(() => {
      document.getElementById('aniation').classList.remove('glitch')
    }, 1000)
    setInterval(() => {
      document.getElementById('aniation').classList.add('glitch')
      setTimeout(() => {
        document.getElementById('aniation').classList.remove('glitch')
      }, 2500)
    }, 8500)
  },

  methods: {
    getRandomToad () {
      const random = Math.random() * 10
      if (random <= 5) {
        this.toad_logo = '/RegularToad.png'
      }
      if (random > 5 && random <= 7.5) {
        this.toad_logo = '/AnotherToad.png'
      }
      if (random > 7 && random <= 9) {
        this.toad_logo = '/BlueToad.png'
      }
      if (random > 9) {
        this.toad_logo = '/DoughnutToad.png'
      }
    },
    goto (refName) {
      const element = this.$refs[refName]
      const topPoint = element.offsetTop
      window.scrollTo({
        top: topPoint,
        left: 0,
        behavior: 'smooth'
      })
    }
  }
}
</script>
<style scoped>

.product-section {
  padding-top: 15vh;
  min-height: 75vh;
}

/*****************/
/* Intro section */
/*****************/

.main-products {
  margin-top: 100px;
}

/************/
/* Partners */
/************/

.partners {
  padding-bottom: 100px;
  text-align: center;
}
.partner-content {
  margin-top: 30px;
  display: inline-block;
  width: 180px;
}
.partner-content img {
  position: relative;
  display: inline-block;
  width: 100%;
  animation: partner-unhover 0.1s linear;
}
.partner-content span {
  text-decoration: none;
  color: white;
  background-color: rgb(43 43 43 / 28%);
  padding: 10px;
  border-radius: 15px;
}

.partner-content:hover > img {
  top: -20px;
  border-radius: 20px;
  background-color: #ffffff0d;
  animation: partner-hover 0.1s linear;
}
@keyframes partner-hover{
  0% {
  top: 0px;
  background-color: #00000000;
  }
  100% {
  top: -20px;
  background-color: #ffffff0d;
  }
}
@keyframes partner-unhover{
  0% {
  top: -20px;
  background-color: #ffffff0d;
  }
  100% {
  top: 0px;
  background-color: #00000000;
  }
}

/****************/
/* Other styles */
/****************/

.v-btn {text-transform: capitalize; font-size:1.1rem; font-weight:400; letter-spacing:1px; height:40px !important;}
.toads-background::before {
  content: "";
  position: absolute;
  top: 0; left: 0;
  width:100%; height: calc(100% + 65px);
  background-image: url('https://www.myjewishlearning.com/wp-content/uploads/2007/12/frogs-plague-vaera-exodus-egyptian-1593x900.jpg');
  filter: opacity(0.05);
  background-size:cover;
  margin-top:-65px;
  background-position: top;
  -webkit-mask-image: -webkit-gradient(linear, left top, left bottom, color-stop(10%,rgba(0,0,0,1)), color-stop(75%,rgba(39, 0, 39, 0)));
  max-height:1000px
}
.second-subtitle {
  letter-spacing:2px !important;
  font-size: 2.0rem !important;
  text-shadow: -2px -2px 0 #000, 2px -2px 0 #000, -2px 2px 0 #000, 2px 2px 0 #000;
}
.second-description {
  margin-top: 30px;
  margin-left:7vw;
  margin-right:7vw;
  font-size: 1.1rem !important;
  letter-spacing: 1px !important;
}
.third-subtitle {
  margin-top:150px;
  letter-spacing:2px !important;
}
.third-description {
  margin-top:40px;
  margin-left:7vw;
  margin-right:7vw;
  font-size: 1.3rem !important;
  letter-spacing: 1px !important;
}
.forth-description {
  margin-top:30px;
  margin-left:7vw;
  margin-right:7vw;
  font-size: 1.3rem !important;
  letter-spacing: 1px !important;
}
.stats {
  font-size: 3.25rem;
  font-weight: 500;
}
.pad-stats {
  font-size: 2.1rem;
  font-weight: 500;
}
.wrapper {
    position: relative;
    padding-bottom: 56.25%;
    /*padding-top: 25px;*/
    width: 100%;
}
.wrapper iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}
@media all and (max-width: 600px) {
  .toads-background::before {
  content: "";
  position: absolute;
  top: 0; left: 0;
  width:100%;
  height: calc(100% + 65px);
  background-image: url('https://www.myjewishlearning.com/wp-content/uploads/2007/12/frogs-plague-vaera-exodus-egyptian-1593x900.jpg');
  filter: opacity(0.05);
  background-size:cover;
  margin-top:-65px;
  background-position-x: -1100px;
  background-position-y: bottom;
  -webkit-mask-image: -webkit-gradient(linear, left top, left bottom, color-stop(10%,rgba(0,0,0,1)), color-stop(80%,rgba(39, 0, 39, 0)));
  max-height:1000px
  }
.wrapper {
    position: relative;
    padding-bottom: 56.25%;   /* 16:9 */
    height: 0;
}
.wrapper iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}
}
.card-title{font-size: 1.6rem !important;  margin-bottom:15px;}

.product-card {
  transition: transform 0.45s cubic-bezier(0.19, 1, 0.22, 1) 0s;
  border-radius: 10px !important;
  background-color: black !important;
  padding-top:10px;
  padding-bottom:10px;
  background-color: rgb(0 0 0);
  border-color: rgb(185 23 23);
  min-width: 200px !important;
  margin: auto;
  max-width: 450px !important;
  min-height: 250px;
}

.product-card:hover {
  transform: translate3d(1px, -3px, 0px);
  cursor: pointer;
  background-color: #191919 !important;
}

.pad-card-title{font-size: 1.6rem !important; font-weight: 500}
.pad-card:hover {
  transform: translate3d(1px, -3px, 0px);
  cursor: pointer;
  background-color: #191919 !important;
}
.pad-card {
  transition: transform 0.45s cubic-bezier(0.19, 1, 0.22, 1) 0s;
  border-radius: 10px !important;
  padding-top:10px;
  padding-bottom:10px;
  background-color: rgb(34 34 34 / 26%);
  border-color: rgb(185 23 23);
  min-width: 200px;
  margin: auto;
  max-width: 450px;
  min-height: 250px;
}

</style>
