<template>
  <div id="app" :style='{ background: "url(" + image + ") no-repeat bottom right, url(" + image2 + ") #191a24" }'>
    <h1>we're launching soon</h1>
    <SocialMedia />
  </div>
</template>

<script>
import SocialMedia from './components/SocialMedia.vue'

export default {
  name: 'App',
  components: {
    SocialMedia
  },
  data() {
    return {
      image: require('@/assets/pattern-hills.svg'),
      image2: require('@/assets/bg-stars.svg'),
      Days: 0,
      Hours: 0,
      Minutes: 0,
      Seconds: 0,
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
    background-color:  hsl(234, 17%, 12%);
  }
  h1 {
    width: fit-content;
    position: absolute;
    top: 120px;
    left: calc(50% - 233px);
    letter-spacing: 5px;
    text-transform: uppercase;
    color: #fff;
    font-size: 28px;
  }
</style>
