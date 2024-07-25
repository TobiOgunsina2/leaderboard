<script setup>
import { ref } from 'vue'
import TableComponent from './components/TableComponent.vue'
import PopUpComponent from './components/PopUpComponent.vue'
const popup = ref(false)
const opp = ref('')

const togglePopUp = (player) => {
  opp.value = player
  popup.value = !popup.value
}
</script>

<template>
  <div class="content" :style="popup ? { opacity: '0.65', filter: 'brightness(70%)' } : {}">
    <h1 class="text-xl my-3 ml-3 text-gray-700">LXG Leaderboard 2024</h1>
    <TableComponent @togglePopUp="togglePopUp" :golf-data="golfData"></TableComponent>
  </div>
  <PopUpComponent :player="opp" :togglePopUp="togglePopUp" v-if="popup"></PopUpComponent>
</template>

<style scoped></style>
