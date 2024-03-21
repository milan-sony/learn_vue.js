<template>

  <h2>Fullname: {{ firstName }} {{ lastName }}</h2>
  <h2>Computed fullname: {{ fullName }}</h2>
  <button @click="changeFullName">Change Name</button>

</template>

<script>

export default {
  name: "App",
  data() {
    return {
      firstName: 'Milan',
      lastName: 'Sony',
    }
  },
  methods: {
    changeFullName(){
      this.fullName = 'Milosh Sony'
    }
  },
  computed:{
    fullName:{
      // getter : read computed property value
      get(){
        return `${this.firstName} ${this.lastName}`
      },
      // setter : set() is called when new value is assigned into the computed property
      set(value){
        const names = value.split(' ')
        this.firstName = names[0]
        this.lastName = names[1]
      }
    }
  }
}

</script>

<style>

</style>
