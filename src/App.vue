<template>
  <div id="app">
    <v-head></v-head>
    <router-view></router-view>
    <v-foot></v-foot>
    <v-mask></v-mask>
    <audio :src="src"  id="audio" :autoplay="isPlaying" loop ref="audio"></audio>
  </div>
</template>

<script>
import vHead from './components/public/header'
import vFoot from './components/public/footer'
import vMask from './components/public/mask'

export default {
  name: 'app',
  components: {
    vHead,
    vFoot,
    vMask
  },
  mounted () {
    console.log(this.$router)
  },
  computed: {
     src() {
      return this.$store.state.src
     },
     isPlaying() {
      return this.$store.state.isPlaying;
    }
  }

}
</script>

<style>

  * {
    margin: 0;
    padding: 0;
  }
  ::-webkit-scrollbar{
    display:none;
  }
  body {
    min-width: 1240px;
    overflow-y: scroll;
    overflow-x: hidden;
  }
  body, button, input, select, textarea, th, a{
    color: #000;
    font-size: 14px;
    line-height: 1.5;
    font-family: poppin, 'PingFang SC',Tahoma,Arial,sans-serif;
  }
  li {
    list-style: none;
  }
  a {
    text-decoration: none;
  }
  img {
    border: 0 none;
  }
</style>
