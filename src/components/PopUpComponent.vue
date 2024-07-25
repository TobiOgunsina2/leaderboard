<script setup>
const props = defineProps(['togglePopUp', 'player'])
</script>

<template>
  <div class="popup rounded-lg shadow-lg bg-white w-1/3 h-1/2">
    <div class="header flex p-2 justify-between">
      <p>Open</p>
      <button
        @click="props.togglePopUp"
        class="text-red-600 hover:text-red-800 w-6 font-bold bg-gray-300 rounded"
      >
        X
      </button>
    </div>
    <p class="mt-5 mb-4 text-center">
      Would you like to challenge <span class="text-blue-600 font-bold">{{ props.player }}</span
      >?
    </p>

    <div class="confirm flex justify-evenly w-full">
      <button class="yes w-1/3 h-10 bg-green-400 hover:bg-green-600 rounded">Yes</button>
      <button class="no w-1/3 h-10 bg-red-400 hover:bg-red-600 rounded">No</button>
    </div>
  </div>
</template>

<style scoped>
.popup {
  position: absolute;
  top: 33%;
  left: 33%;
}
</style>
