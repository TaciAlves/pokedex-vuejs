<template>
    <div class="container">
        <div class="header">
            <img class="title" src="../assets/header.svg">
        </div>
        <h3>&copy; 2022. Desenvolvido por Taciara.</h3>
      
      <PokemonSearch 
        :apiUrl="apiUrl" 
        @setPokemonUrl="setPokemonUrl" 
        />
      <PokemonList 
        :imageUrl="imageUrl" 
        :apiUrl="apiUrl"
        @setPokemonUrl="setPokemonUrl" 
        />
      <PokemonDetail 
        v-if="showDetail"
        :pokemonUrl="pokemonUrl"
        :imageUrl="imageUrl"
        @closeDetail="closeDetail" 
        />
    </div>
  </template>
  
  <script>
    import PokemonSearch from './PokemonSearch.vue';
    import PokemonList from './PokemonList.vue';    
    import PokemonDetail from './PokemonDetails.vue';
    export default {
      data: () => {
        return {
          imageUrl: 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/',
          apiUrl: 'https://pokeapi.co/api/v2/pokemon/',
          pokemonUrl: '',
          showDetail: false
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
    
    @import url('https://fonts.googleapis.com/css2?family=Play:wght@400;700&display=swap');

    .container {
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      padding: 10px;
      width: calc(100% - 20px);
      min-height: calc(100vh - 20px);
      background-image: url(../assets/bg.png);
      background-size: cover;
      background-repeat: no-repeat;
      font-family: 'Play', sans-serif;
      font-size: 1rem;
      font-weight: normal;
    }

    h3 {
        color: #efefef; 
        padding-bottom: 15px;
    }

    .header {
        display: flex;
        justify-content: center;
        align-items: center;
        padding-bottom: 15px;
    }

    .header .title {
        width: 100%;
        height: 100px;
    }
    
  </style>