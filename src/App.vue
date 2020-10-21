<template>
  <div>  
    <h1>Rick and Morty Characters</h1>
    <div>
      <form >
        <select name="characters" id="character-list" v-model="selectedCharacter">
          <option value="" disabled selected>Select your character</option>
          <option v-for='(character, index) in characters.results' :key="index" :value="character">{{character.name}}</option>
        </select>
      </form>
       <img v-if="selectedCharacter" :src="selectedCharacter.image" alt="flag picture">
      <!-- <characters-list :characters='characters'></characters-list> -->
      <character-detail :character="selectedCharacter"></character-detail>
    </div>
  </div>
</template>

<script>
import CharactersList from './components/CharactersList.vue'
import {eventBus} from '@/main.js'; 
import CharacterDetail from './components/CharacterDetail.vue'
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
  eventBus.$on('character-selected', (character) => {
    this.selectedCharacter = character;
  })
  },
  components: {
    "characters-list": CharactersList,
    "character-detail": CharacterDetail
  }
}
</script>

<style>

</style>