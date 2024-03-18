<template>

  <h2 v-for="name in names" :key="name">{{ name }}</h2>
  <h2 v-for="(name, index) in names" :key="name">{{index}} {{ name }}</h2>
  <h2 v-for="(name, index) in names" :key="name">{{index + 1}} {{ name }}</h2>

</template>

<script>

export default {
  name: "App",
  data() {
    return {
      names: ['milan', 'sony']
    }
  }
}

</script>

<style></style>
