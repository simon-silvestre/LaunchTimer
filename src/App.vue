<template>
  <div id="app" :style='{ background: "url(" + image + ") no-repeat bottom right / contain, url(" + image2 + ") #201f2b" }'>
    <h1>we're launching soon</h1>
    <SocialMedia />
    <div class="temps">
      <Horaires :chiffre="Days" name="days" />
      <Horaires :chiffre="Hours" name="hours" />
      <Horaires :chiffre="Minutes" name="minutes" />
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
      Days: '08',
      Hours: '23',
      Minutes: '55',
      Seconds: '41',
    }
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
    position: absolute;
    top: 260px;
    left: calc(50% - 360px);
  }
</style>
