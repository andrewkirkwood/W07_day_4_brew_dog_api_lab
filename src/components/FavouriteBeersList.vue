<template lang="html">
  <div>
    <ul>
      <beer-list-item v-for="(beer) in favouriteBeers" :beer="beer"></beer-list-item>
    </ul>
  </div>
</template>

<script>
import {eventBus} from '../main.js'
import BeerListItem from './BeerListItem.vue'

export default {
  name: 'favourite-beers',
  props: ['favouriteBeers'],
  components: {
    "beer-list-item": BeerListItem
  }

}
</script>

<style lang="css" scoped>
</style>
