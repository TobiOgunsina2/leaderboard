<template>
  <div class="flex justify-center">
    <div
      class="w-full flex"
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
        class="border bg-gray-100 font-medium text-md h-9 w-full rounded-lg text-center grid items-end"
        v-if="
          this.params.node.rowIndex > 0 &&
          this.params.api.getDisplayedRowAtIndex(this.params.node.rowIndex).data.status != 'Ongoing'
        "
      >
        <svg
          class="justify-self-end"
          xmlns="http://www.w3.org/2000/svg"
          width="30px"
          height="30px"
          viewBox="0 0 24 24"
          fill="currentColor"
        >
          <path
            d="M12 15.0006L7.75732 10.758L9.17154 9.34375L12 12.1722L14.8284 9.34375L16.2426 10.758L12 15.0006Z"
          ></path>
        </svg>
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

<style></style>
