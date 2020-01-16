<template lang="html">
  <article v-if="beer">
    <h3> {{ beer.name }}</h3>
    <dl>
      <dt>Tagline:</dt>
    <dd>{{ beer.tagline }}</dd>

    <dt>First Brewed:</dt>
    <dd>{{ beer.first_brewed }}</dd>

    <dt>Description:</dt>
    <dd>{{ beer.description }}</dd>
    </dl>

    <button v-on:click="handleSubmit" type="submit" name="button">Make favourite</button>

  </article>
</template>

<script>
import {eventBus} from '../main.js'

export default {
  name: 'beer-detail',
  props: ['beer'],
  methods: {
    handleSubmit() {
      eventBus.$emit('favourite-beer-selected', this.beer)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
