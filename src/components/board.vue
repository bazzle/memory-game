<template>
  <div class="board">
    <div class="board__inner">
      <!-- v-for is looping cards array -->
      <!-- cards the prop that card item accepts, we're passing it 'item', which is one object of the array, the properties of which will be used in the cardItem component -->
      <card v-for="item in this.shuffledCards" v-bind:cardProp="item" v-bind:key="item.id" />
    </div>
  </div>
</template>

<script>
import card from './card.vue'
export default {
  name: 'board',
  components: {
    card
  },
  data: function () {
    return {
      cards: [
        {
          name: 'daruma',
          color: 'yellow'
        },
        {
          name: 'crab',
          color: 'purple'
        },
        {
          name: 'daruma',
          color: 'yellow'
        },
        {
          name: 'crab',
          color: 'purple'
        }
      ],
      shuffledCards: [
      ]
    }
  },
  methods: {
    shuffler: function (arra1) {
      let ctr = arra1.length
      let temp
      let index
      while (ctr > 0) {
        index = Math.floor(Math.random() * ctr)
        ctr--
        temp = arra1[ctr]
        arra1[ctr] = arra1[index]
        arra1[index] = temp
      }
      return arra1
    }
  },
  mounted: function () {
    let newOrder = this.shuffler(this.cards)
    this.shuffledCards = newOrder
    console.log(this.shuffledCards)
  },
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .board{
    width:100%;
    max-width:800px;
    height:0;
    padding-bottom:50%;
    position:relative;
    &__inner{
      position:absolute;
      top:0;
      left:0;
      width:100%;
      height:100%;
      display:grid;
      grid-template-columns:1fr 1fr;
      grid-template-rows:1fr 1fr;
      grid-gap:10px;
    }
  }
</style>
