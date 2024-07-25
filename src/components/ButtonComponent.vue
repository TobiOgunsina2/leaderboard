<template>
  <div
    class="w-full"
    v-if="
      this.params.col > this.params.row + 1 ||
      this.params.col == 0 ||
      (this.params.row > 2) & (this.params.col < 2)
    "
  >
    <button
      v-if="this.params.node.rowIndex > 0"
      @click="
        () =>
          this.params.showChallenger(
            this.params.api.getDisplayedRowAtIndex(this.params.node.rowIndex - this.params.col - 1)
              .data.player
          )
      "
      class="text-gray-900 font-medium text-md h-9 w-full rounded-lg text-center hover:text-green-500"
    >
      {{
        this.params.api.getDisplayedRowAtIndex(this.params.node.rowIndex - this.params.col - 1).data
          .player
      }}
    </button>
    <button v-else><p class="text-center mx-auto w-full">X</p></button>
  </div>
  <button v-else>
    <p class="text-center mx-auto w-full">X</p>
  </button>
</template>

<script>
export default {
  data() {
    return {}
  },
  methods: {
    sayHello() {
      console.log('hi')
    },
    getNum() {
      this.params.num
    }
  },
  setup() {}
}
</script>
