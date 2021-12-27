<template>
  <div id="app">
    <div id="wrapper" style="margin-top:80px">
      <img :src="toad_logo" style="height: 115px; position:sticky; margin-bottom:10px">
      <h1
      id="aniation"
      class="text-glitch glitch"
      data-text="TOADmap"
      style="color:#8ad98a;letter-spacing: 0.15em; margin-bottom:25px; font-size: calc(30px + 2vw)">
      TOADmap
      </h1>
    </div>

  <div>
    <Roadmap/>
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
