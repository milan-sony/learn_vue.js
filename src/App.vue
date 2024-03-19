<template>

  <h2>{{ 10 + 20 }}</h2>

  <h2>Add method {{ add(2, 3, 5) }}</h2>
  <h2>Add method {{ add(2, 3, 2) }}</h2>
  <h2>multiply {{ multiply(5) }}</h2>

</template>

<script>

export default {
  name: "App",
  data() {
    return {
      baseMultiplier:5
    }
  },
  methods:{
    add(num1, num2, num3){
      return num1 + num2 + num3
    },
    multiply(num){
      return num * this.baseMultiplier
    }
  }
}

</script>

<style></style>
