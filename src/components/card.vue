<template>
    <div :class="`card card--${cardProp.color}`">
    <inline-svg :src="require('../assets/icons/' + cardProp.name + '.svg')" width="150" height="150" :fill="cardProp.color"/>
  </div>
</template>
<script>
import InlineSvg from 'vue-inline-svg'
export default {
  name: 'card',
  props: ['cardProp'],
  components: {
    InlineSvg
  }
}
</script>
<style scoped>
  .card{
    color:white;
    margin:4px;
    display:flex;
    justify-content: center;
    align-items: center;
    border:4px solid blueviolet;
    border-radius: 8px;
  }
</style>
