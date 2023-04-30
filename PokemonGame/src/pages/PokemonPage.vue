<script src="./pokemonPage.ts"/>

<template>

    <h1 v-if="!pokemon"> Espere por favor... </h1>
    <div v-else>
    <!-- Img Pokemon -->
    <PokemonPicture :pokemonId="pokemon.id" :showPokemon="showPokemon"/>
    <!-- Opciones Pokemon -->
    <PokemonOptions :pokemons="pokemonArr" @selection-pokemon="checkAnsware"/>

    <template v-if="showAnswer">
      <h2 class="fade-in"> {{ message }}</h2>
      <button @click="newGame">
        Nuevo juego
      </button>
    </template>

    </div>
</template>

<!--
<style scoped>

</style>-->