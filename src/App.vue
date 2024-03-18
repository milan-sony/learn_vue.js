<template>

  <h2 v-if="num === 0">The number is Zero</h2>
  <h2 v-else>The number is not Zero</h2>

</template>

<script>

export default {
  name: "App",
  data() {
    return {
      num: 5
    }
  }
}

</script>

<style>

</style>
