<template>
  <div class="flex justify-center">
    <div
      class="w-full flex justify-center"
      v-if="
        (this.params.node.rowIndex - this.params.col - 1 > 0 &&
          this.params.col > this.params.row + 1) ||
        this.params.col == 0 ||
        (this.params.row > 3) & (this.params.col < 2) ||
        (this.params.row > 7) & (this.params.col < 3) ||
        (this.params.row > 11) & (this.params.col < 4)
      "
    >
      <button
        v-if="
          this.params.node.rowIndex > 0 &&
          this.params.api.getDisplayedRowAtIndex(this.params.node.rowIndex).data.status != 'Ongoing'
        "
        @click="
          () =>
            this.params.showChallenger(
              this.params.api.getDisplayedRowAtIndex(
                this.params.node.rowIndex - this.params.col - 1
              ).data.player
            )
        "
        :class="`text-gray-900 font-medium text-md h-9 w-full hover:shadow-lg shadow-md rounded-lg text-center ${
          this.params.api.getDisplayedRowAtIndex(this.params.node.rowIndex - this.params.col - 1)
            .data.status == 'Ongoing'
            ? 'line-through text-red-500'
            : 'hover:text-blue-900'
        } `"
      >
        {{
          this.params.api
            .getDisplayedRowAtIndex(this.params.node.rowIndex - this.params.col - 1)
            .data.player.substring(0, 5)
        }}
      </button>
      <button
        v-else-if="
          this.params.node.rowIndex > 0 &&
          this.params.col == 0 &&
          this.params.api.getDisplayedRowAtIndex(this.params.node.rowIndex).data.status == 'Ongoing'
        "
        @click="
          () =>
            this.params.showChallenger(
              this.params.api.getDisplayedRowAtIndex(
                this.params.node.rowIndex - this.params.col - 1
              ).data.player
            )
        "
        class="text-white bg-green-400 font-medium text-md h-9 w-full hover:shadow-lg shadow-md rounded-lg text-center"
      >
        {{ this.params.data.match }}
      </button>
      <button v-else><p class="text-center mx-auto w-full text-blue-500 font-bold">-</p></button>
    </div>
    <button v-else>
      <p class="text-center mx-auto w-full text-blue-500 font-bold">-</p>
    </button>
  </div>
</template>

//Possible player // Contender // Challger

<script>
export default {
  data() {
    return {}
  },
  methods: {
    sayHello() {
      console.log('hi')
    }
  },
  mounted() {},
  setup() {}
}
</script>
