<template>

  <h2>Volume Tracker (0-20)</h2>
  <h2>Current Volume {{ volume }}</h2>
  <div>
    <button @click="volume += 2">Increase</button>
    <button @click="volume -= 2">Decrease</button>
  </div>

</template>

<script>

export default {
  name: "App",
  data() {
    return {
      volume: 0
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
    }
  }
}

</script>

<style></style>
