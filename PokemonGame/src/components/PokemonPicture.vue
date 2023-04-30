<script setup lang="ts">
import { computed } from 'vue';

//Tarea
const props = defineProps<{pokemonId: number, showPokemon:boolean}>();
const imgSrc = computed(() => `https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/${props.pokemonId}.svg`);

</script>

<template>
    <div class="pokemon-container">
    <img
      v-if="!showPokemon"
      class="hidden-pokemon"
      :src="imgSrc"
      alt="">

      <img
      v-else
      class="fade-in"
      :src="imgSrc"
      alt="">
    </div>

</template>

<style scoped>

.pokemon-container {
    height: 200px;
}

img {
    height: 200px;
    /* Para que esté una imagen sobre otra */ 
    position: absolute;
    width: 100vw;
    right: 0;
    /* Para que el usuario no haga drag con las imagenes */ 
    user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    -webkit-user-drag: none;
    -webkit-user-select: none;
}

.hidden-pokemon {
    /* brillo a 0 para que la imagen se vea en color*/
    filter: brightness(0);
}

</style>