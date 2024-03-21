<template>

  <h2>Fullname: {{ firstName }} {{ lastName }}</h2>
  <h2>Computed fullname: {{ fullName }}</h2>

  <h2>Computed total: {{ total }}</h2>
  <h2>Method Total: {{ getTotal() }}</h2>
  <input type="text" v-model="country">

</template>

<script>

export default {
  name: "App",
  data() {
    return {
      firstName: 'Milan',
      lastName: 'Sony',
      items: [
        {
          id: 1,
          title: 'TV',
          price: 100
        },
        {
          id: 1,
          title: 'Phone',
          price: 200
        },
        {
          id: 1,
          title: 'Laptop',
          price: 300
        },
      ],
      country: ''
    }
  },
  methods: {
    getTotal(){
      console.log('getTotal()')
      return this.items.reduce((total, curr) => (total = total + curr.price), 0)
    }

  },
  computed:{
    fullName(){
      return `${this.firstName} ${this.lastName}`
    },
    total(){
      console.log('total()')
      return this.items.reduce((total, curr) => (total = total + curr.price), 0)
    }
  }
}

</script>

<style>

</style>
