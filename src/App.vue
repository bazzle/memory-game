<template>
  <div id="app">
    <board />
    <div v-if="instructions" class="instructions">
      {{ instruction_string }}
    </div>
  </div>
</template>

<script>
import board from './components/board.vue'

export default {
  name: 'app',
  components: {
    board
  },
  data: function () {
    return {
      item: '',
      cardProp: '',
      instructions: true,
      instruction_string: 'Click to flip'
    }
  }
}
</script>

<style lang="scss">
html, body{
  width:100%;
  height:100%;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  overflow:hidden;
  margin:0;
  padding:0;
}
#app{
  display:flex;
  align-items:center;
  justify-content:center;
  width:100%;
  height:100%;
  background-color:rgb(48, 48, 48);
  flex-direction: column;
}
.instructions{
  color:white;
  padding:3em;
  text-transform:uppercase;
}
</style>
