<template>
  <div class="pokemon-card" @click="$emit('click', pokemon)">
    <img :src="pokemon.imageUrl" :alt="pokemon.name" />
    <h3>{{ pokemon.name }}</h3>
  </div>
</template>

<script>
export default {
  props: {
    pokemon: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style>
.pokemon-card {
  /* Add styling for the pokemon card */
}
</style>
