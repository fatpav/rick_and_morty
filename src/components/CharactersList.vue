<template lang="html">
<div>
    <ul>
        <character-select v-for="(character, index) in characters.results" :character="character" :key="index"></character-select>
    </ul>
</div>
  
</template>

<script>
import CharacterSelect from './CharacterSelect.vue'

export default {
    name: 'characters-list',
    props: ['characters'],
    components: {
        'character-select': CharacterSelect
    }

}
</script>

<style>

</style>