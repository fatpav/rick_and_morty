<template>
  <article v-if="character">
      <h3>{{character.name}}</h3>
      <p>{{character.species}}</p>
      <p>{{character.gender}}</p>
  </article>
</template>

<script>
export default {
    name: 'character-detail',
    props: ['character']

}
</script>

<style>

</style>