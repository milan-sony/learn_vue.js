<template>

  <h2>Volume Tracker (0-20)</h2>
  <h2>Current Volume {{ volume }}</h2>
  <div>
    <button @click="volume += 2">Increase</button>
    <button @click="volume -= 2">Decrease</button>
  </div>
  <input type="text" v-model="movie">

</template>

<script>

export default {
  name: "App",
  data() {
    return {
      volume: 0,
      movie: 'Batman'
    }
  },
  methods: {

  },
  computed: {

  },
  watch: {
    volume(newValue, oldValue) {
      if (newValue > oldValue && newValue === 16) {
        alert("Volume above 16")
      }
    },
    movie:{
      handler(newValue){
        console.log(`Calling an API with the movie name = ${newValue}`)
      },
      immediate: true
    }
  }
}

</script>

<style></style>
