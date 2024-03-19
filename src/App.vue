<template>

  <h2>{{ name }}</h2>
  <div>
    <button v-on:click="name = 'sony'">Change name</button>
  </div>

  <h2>{{ count }}</h2>
  <div>
    <button v-on:click="count ++">Increment</button>
    <button v-on:click="count --">Decrement</button>
  </div>

</template>

<script>

export default {
  name: "App",
  data() {
    return {
      name: 'milan',
      count: 0
    }
  },
  methods:{

  }
}

</script>

<style></style>
