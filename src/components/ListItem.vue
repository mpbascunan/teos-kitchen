<template>
  <div class="container">
    <v-btn @click="pickRandomItem" id="random-recipe-btn" class="mb-5"> Pick Random Recipe! </v-btn>
    <v-dialog v-model="isDialogOpen" max-width="400">
      <v-card v-if="selectedItem">
        <v-card-title>Your recipe</v-card-title>

        <v-card-text>
          <p>{{ selectedItem.name }}</p>
          <p>{{ selectedItem.recipe }}</p>
        </v-card-text>

        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn variant="text" @click="isDialogOpen = false">Close</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
    <div class="list-item">
      <div v-for="item in items" :key="item.name" class="item">
        <v-btn @click="selectItem(item)" block variant="text">{{ item.name }}</v-btn>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
interface Props {
  items: { name: string; recipe: string }[]
}
const isDialogOpen = ref(false)
const selectedItem = ref({ name: '', recipe: '' })

// Main function
const pickRandomItem = () => {
  if (props.items.length === 0) return

  // Randomization logic
  const randomIndex = Math.floor(Math.random() * props.items.length)

  // Assign the item and open the dialog
  selectedItem.value = props.items[randomIndex]
  isDialogOpen.value = true
}

const selectItem = (item: { name: string; recipe: string }) => {
  selectedItem.value = item
  isDialogOpen.value = true
}

const props = defineProps<Props>()
</script>

<style scoped>
.list-item {
  margin-top: 10px;
  text-align: center;
}
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}
#random-recipe-btn {
  background-color: var(--vt-c-primary);
}
</style>
