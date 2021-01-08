<template>
  <div id="app" :style='[bigView ? { background: "url(" + image + ") no-repeat bottom right, url(" + image2 + ") #201f2b" } : { background: "url(" + image + ") no-repeat bottom right / contain, url(" + image2 + ") #201f2b" } ]'>
    <h1>we're launching soon</h1>
    <SocialMedia />
    <div class="temps">
      <Horaires :chiffre="Days" name="days" />
      <Horaires :chiffre="Hours" name="hours" />
      <Horaires :chiffre="Minutes" name="Minutes" />
      <Horaires :chiffre="Seconds" name="seconds" />
    </div>
  </div>
</template>

<script>
import SocialMedia from './components/SocialMedia.vue'
import Horaires from './components/Horaires.vue'

export default {
  name: 'App',
  components: {
    SocialMedia,
    Horaires
  },
  data() {
    return {
      image: require('@/assets/pattern-hills.svg'),
      image2: require('@/assets/bg-stars.svg'),
      Days: 0,
      Hours: 0,
      Minutes: 0,
      Seconds: 0,
      tempsRestant: Number,
      bigView: false,
    }
  },
  methods: {
    handleView() {
      this.bigView = window.innerWidth <= 1440;
    },
    launch() {
      this.tempsRestant= (new Date("2022", "00", "01", "00", "00", "00").getTime() - new Date()) / 1000
      
      if (this.tempsRestant > 0) {
        this.Days    = Math.floor(this.tempsRestant / 86400);
        this.Hours   = Math.floor((this.tempsRestant - (this.Days * 86400)) / 3600);
        this.Minutes  = Math.floor((this.tempsRestant - (this.Days * 86400 + this.Hours * 3600)) / 60);
        this.Seconds  = Math.floor(this.tempsRestant - (this.Days * 86400 + this.Hours * 3600 + this.Minutes * 60))
      }
    }
  },
  created() {
    this.handleView();
      window.addEventListener('resize', this.handleView);
      setInterval(this.launch, 1000);
  }
}
</script>

<style lang="scss">
  @import url('https://fonts.googleapis.com/css2?family=Red+Hat+Text:wght@700&display=swap');
  * {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
  }
  #app {
    display: flex;
    justify-content: center;
    align-items: center;
    font-family: 'Red Hat Text', sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    width: 100%;
    height: 100vh;
    background-color:  #201f2b;
  }
  h1 {
    width: fit-content;
    position: absolute;
    top: 120px;
    left: calc(50% - 212.5px);
    letter-spacing: 5px;
    text-transform: uppercase;
    color: #fff;
    font-size: 25px;
  }
  .temps {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    margin-bottom: 100px;
  }
</style>
