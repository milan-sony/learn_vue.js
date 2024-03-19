<template>

  <h2>{{ 10 + 20 }}</h2>

  <h2>Add method {{ add() }}</h2>

</template>

<script>

export default {
  name: "App",
  data() {
    return {

    }
  },
  methods:{
    add(){
      return 2+3+5
    }
  }

}

</script>

<style></style>
