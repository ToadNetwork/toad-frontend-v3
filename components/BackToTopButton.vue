<template>
  <div
  id="pagetop"
  style="position: fixed; bottom: 10px; right: 10px;"
  v-show="scY > 300"
  @click="toTop"
  >
    <p>Back to top</p>
    <v-icon aria-label="My Account" role="img" aria-hidden="false">
    mdi-arrow-up
    </v-icon>
  </div>
</template>

<script>
export default {
  data () {
    return {
      scTimer: 0,
      scY: 0
    }
  },
  mounted () {
    window.addEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll () {
      if (this.scTimer) { return };
      this.scTimer = setTimeout(() => {
        this.scY = window.scrollY
        clearTimeout(this.scTimer)
        this.scTimer = 0
      }, 100)
    },
    toTop () {
      window.scrollTo({
        top: 0,
        behavior: 'smooth'
      })
    }
  }
}
</script>

<style scoped>
#pagetop {
  display: block;
  border: 1px solid #32323282;
  border-radius: 10px;
  background-color: #9d9d9d1f;
  z-index: 999999;
  padding-top: 15px;
  padding-left: 12px;
  padding-right: 10px;
}
#pagetop p {
  display: inline-block;
}
#pagetop svg {
  display: inline-block;
  padding-top: 15px;
}
#pagetop:hover {
  background-color: rgb(88 138 184 / 30%);
  cursor: pointer;
}
</style>
