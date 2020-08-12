<template lang="">
    <div class="">
        <div class="container">
            <img alt="Pokemon Logo" src="../assets/pokemon_logo.gif">
            <PokemonSearch 
                :apiUrl="apiUrl" 
                @setPokemonUrl="setPokemonUrl" />
            <PokemonList 
                :imageUrl="imageUrl"
                :imageShinyUrl="imageShinyUrl" 
                :apiUrl="apiUrl"
                @setPokemonUrl="setPokemonUrl" />
            <PokemonDetail 
                v-if="showDetail"
                :pokemonUrl="pokemonUrl"
                :imageUrl="imageUrl"
                :imageShinyUrl="imageShinyUrl"
                @closeDetail="closeDetail" />
        </div>
    </div>
</template>
<script>
import PokemonDetail from './PokemonDetail.vue';
import PokemonSearch from './PokemonSearch.vue';
import PokemonList from './PokemonList.vue';

export default {
    data: () => {
        return {
             imageUrl: 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/',
             apiUrl: 'https://pokeapi.co/api/v2/pokemon/',
             pokemonUrl: '',
             showDetail: false,
             imageShinyUrl: 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/shiny/'
        }
    },
    components: {
         PokemonSearch,
         PokemonList,
         PokemonDetail
    },
    methods: {
      setPokemonUrl(url) {
        this.pokemonUrl = url;
        this.showDetail = true;
      },
      closeDetail() {
        this.pokemonUrl = '';
        this.showDetail = false;
      }
    } 
}
</script>
<style lang="scss" scoped>
  @import url('https://fonts.googleapis.com/css?family=Acme');
  .container {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    padding: 10px;
    width: calc(100% - 20px);
    min-height: calc(100vh - 20px);
    background: radial-gradient(#156F99, #d80c0c);
    font-family: 'Acme', arial;
    font-size: 1rem;
    font-weight: normal;
  }
  h1 { color: #efefef; }
</style>