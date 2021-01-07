<template>
  <div id="app" :style='{ background: "url(" + image + ") no-repeat bottom right, url(" + image2 + ") #191a24" }'>
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
      image2: require('@/assets/bg-stars.svg')
    }
  }
}
</script>

<style lang="scss">
  * {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
  }
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    width: 100%;
    height: 100vh;
    background-color:  hsl(234, 17%, 12%);
  }
</style>
