<template>
  <div class="w-full h-full flex items-center justify-center">
    <svg
      v-if="this.params.data.status == 'X'"
      class="w-5/6 h-5/6"
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 24 24"
      fill="rgb(36, 193, 255)"
    >
      <path
        d="M12 22C6.47715 22 2 17.5228 2 12C2 6.47715 6.47715 2 12 2C17.5228 2 22 6.47715 22 12C22 17.5228 17.5228 22 12 22ZM9 9V15H11V9H9ZM13 9V15H15V9H13Z"
      ></path></svg
    ><svg
      v-if="this.params.data.status == ''"
      class="w-5/6 h-5/6"
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 24 24"
      fill="rgb(36, 193, 255)"
    >
      <path
        d="M12 22C6.47715 22 2 17.5228 2 12C2 6.47715 6.47715 2 12 2C17.5228 2 22 6.47715 22 12C22 17.5228 17.5228 22 12 22ZM12 20C16.4183 20 20 16.4183 20 12C20 7.58172 16.4183 4 12 4C7.58172 4 4 7.58172 4 12C4 16.4183 7.58172 20 12 20ZM10.6219 8.41459L15.5008 11.6672C15.6846 11.7897 15.7343 12.0381 15.6117 12.2219C15.5824 12.2658 15.5447 12.3035 15.5008 12.3328L10.6219 15.5854C10.4381 15.708 10.1897 15.6583 10.0672 15.4745C10.0234 15.4088 10 15.3316 10 15.2526V8.74741C10 8.52649 10.1791 8.34741 10.4 8.34741C10.479 8.34741 10.5562 8.37078 10.6219 8.41459Z"
      ></path>
    </svg>
    <svg
      v-if="this.params.data.status == 'Ongoing'"
      class="w-5/6 h-5/6"
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 24 24"
      fill="rgb(36, 193, 255)"
    >
      <path
        d="M19.376 12.4161L8.77735 19.4818C8.54759 19.635 8.23715 19.5729 8.08397 19.3432C8.02922 19.261 8 19.1645 8 19.0658V4.93433C8 4.65818 8.22386 4.43433 8.5 4.43433C8.59871 4.43433 8.69522 4.46355 8.77735 4.5183L19.376 11.584C19.6057 11.7372 19.6678 12.0477 19.5146 12.2774C19.478 12.3323 19.4309 12.3795 19.376 12.4161Z"
      ></path>
    </svg>
  </div>
</template>

<script>
export default {
  data() {
    return {}
  },
  methods: {
    sayHello() {
      console.log(this.params.data.status)
    }
  },
  setup() {}
}
</script>

<style scoped>
@media screen and (max-width: 450px) {
  svg,
  path {
    width: 150%;
    height: 150%;
  }
}
</style>
