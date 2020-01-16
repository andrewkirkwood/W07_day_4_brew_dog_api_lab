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
  </article>
</template>

<script>
export default {
  name: 'beer-detail',
  props: ['beer']
}
</script>

<style lang="css" scoped>
</style>
