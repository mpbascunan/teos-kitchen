<template>
  <MainHeader />
  <MainTitle />
  <ListItem :items="items" />
</template>

<script setup lang="ts">
import { ref } from 'vue'
import MainHeader from './components/MainHeader.vue'
import ListItem from './components/ListItem.vue'
import MainTitle from './components/MainTitle.vue'

const items = ref([
  {
    name: 'Tortilla de acelga',
    recipe: 'Cook acelga, mix with eggs, and cook in a pan.',
  },
  { name: 'Tofu salteado', recipe: 'Stir-fry tofu with vegetables and soy sauce.' },
  { name: 'Huevo revuelto', recipe: 'Scramble eggs with vegetables and serve.' },
  { name: 'Sopa de fideos', recipe: 'Cook fideos, serve in broth with toppings.' },
  { name: 'Omelette', recipe: 'Beat eggs, cook in a pan, add fillings, and fold.' },
  { name: 'Ensalada de garbanzos', recipe: 'Mix canned chickpeas with vegetables and dressing.' },
  { name: 'Hummus', recipe: 'Blend chickpeas, tahini, lemon juice, and garlic until smooth.' },
  { name: 'Ramen', recipe: 'Cook ramen noodles, add broth, and top with vegetables.' },
  { name: 'Tallarines', recipe: 'Cook tallarines, serve with sauce and toppings.' },
])
</script>

<style scoped></style>
