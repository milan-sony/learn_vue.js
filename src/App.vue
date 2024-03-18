<template>

  <h2 v-if="num === 0">The number is Zero</h2>
  <h2 v-else>The number is not Zero</h2>

  <div v-if="display">
    <p>Inside div tag</p>
    <h2>Name: Milan Sony</h2>
    <h2>Age: 23</h2>
  </div>

  <template v-if="display">
    <p>No div tag its inside template tag</p>
    <p>The template tag acts as an invisible wrapper</p>
    <h2>Name: Milan Sony</h2>
    <h2>Age: 23</h2>
  </template>

</template>

<script>

export default {
  name: "App",
  data() {
    return {
      num: 5,
      display: true
    }
  }
}

</script>

<style></style>
