<template>
  <div class="card">
    Card
    <icons iconName="daruma" />
  </div>
</template>
<script>
import icons from './icons'
export default {
  name: 'cardItem2',
  components: {
    icons
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
