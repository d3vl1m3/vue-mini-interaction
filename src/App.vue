<template>
  <div id="app">
    <MiniInteraction/>
  </div>
</template>

<script>
import MiniInteraction from './components/MiniInteraction.vue'

export default {
  name: 'app',
  components: {
    MiniInteraction
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'open Sans', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
