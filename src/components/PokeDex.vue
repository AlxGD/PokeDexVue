<template>
  <div class="pokedex">
    <div class="card-grid">
      <PokemonCard v-for="pokemon in pokemonList" :key="pokemon.id" :pokemon="pokemon" @click="showDetails(pokemon)" />
    </div>
    <div v-if="selectedPokemon" class="pokemon-details">
      <!-- Display Pokémon details here -->
      <h2>{{ selectedPokemon.name }}</h2>
      <img :src="selectedPokemon.imageUrl" :alt="selectedPokemon.name" />
    </div>
  </div>
</template>

<script>
import PokemonCard from './PokemonCard.vue';

export default {
  data() {
    return {
      pokemonList: [], // Placeholder for Pokémon data
      selectedPokemon: null, // Holds the currently selected Pokémon
    };
  },
  methods: {
    showDetails(pokemon) {
      this.selectedPokemon = pokemon;
    },
  },
  components: {
    PokemonCard,
  },
};
</script>

<style>
.pokedex {
  /* Add styling for the pokedex container */
}

.card-grid {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  gap: 10px;
}

.pokemon-details {
  /* Add styling for the Pokémon details container */
}
</style>
