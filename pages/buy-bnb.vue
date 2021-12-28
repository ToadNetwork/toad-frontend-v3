<template>
  <div id="app">
    <div id="wrapper" style="margin-top:80px">
      <img :src="toad_logo" style="height: 115px; position:sticky; margin-bottom:10px">
      <h1
      id="aniation"
      class="text-glitch glitch"
      data-text="Buy BNB with fiat"
      style="color:#8ad98a;letter-spacing: 0.15em; margin-bottom:25px; font-size: calc(30px + 2vw)">
      Buy BNB with fiat
      </h1>
    </div>

    <div class="onramper-container">
      <Onramper/>
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

.onramper-container {
  display: flex;
  width: 100%;
  height: 800px;
  flex-direction: column;
  overflow: hidden;
}

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
}

</style>
