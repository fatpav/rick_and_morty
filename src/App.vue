<template>
  <h1>Hello guys</h1>
</template>

<script>
export default {
  name: 'app',
  data() {
    return {
      characters: [],
      selectedCharacter: null
    };
  },
  mounted(){
    fetch('https://rickandmortyapi.com/api/character')
    .then(res => res.json())
    .then(characters => this.characters = characters)
  }

}
</script>

<style>

</style>