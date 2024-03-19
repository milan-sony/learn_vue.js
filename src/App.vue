<template>

  <h2>{{ name }}</h2>
  <div>
    <button @:click="changeName(), increment(1)">Change name</button>
  </div>

  <h2>{{ count }}</h2>
  <div>
    <button v-on:click="increment(1)">Increment</button>
    <button v-on:click="decrement(1)">Decrement</button>
    <button v-on:click="increment(5)">Increment</button>
    <button v-on:click="decrement(5)">Decrement</button>
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
    changeName(){
      this.name = "Sony"
    },
    increment(num){
      this.count += num
    },
    decrement(num){
      this.count -= num
    }
  }
}

</script>

<style></style>
