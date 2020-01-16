<template lang="html">
  <div>
    <ul>
      <!-- <li v-for="beer in beers" v-on:click="handleClick">{{beer.name}}</li> -->
      <beer-list-item v-for="(beer) in beers" :beer="beer"></beer-list-item>
    </ul>
  </div>

</template>

<script>
// import BeerListItem from './BeerListItem.vue'
import {eventBus} from '../main.js'
import BeerListItem from './BeerListItem.vue'


export default {
  name: 'all-beers-list',
  props: ['beers'],
  methods: {
    // handleClick() {
    //   eventBus.$emit('beer-selected', this.beer)

    // }
  },
  components: {
    "beer-list-item": BeerListItem
  }
}
</script>

<style lang="css" scoped>
</style>
