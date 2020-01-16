<template lang="html">
  <div>
    <ul>
      <li v-for="beer in beers">{{beer.name}}</li>
      <!-- <beer-list-item >  {{beers}}    </beer-list-item> -->
    </ul>
  </div>

</template>

<script>
import BeerListItem from './BeerListItem.vue'

export default {
  name: 'all-beers-list',
  props: ['beers'],
  components: {
    // "beer-list-item": BeerListItem
  }
}
</script>

<style lang="css" scoped>
</style>
