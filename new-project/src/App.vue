<template>
  <GreetMe name="Milan" />
  <GreetMe :name="name" :email="email" />
</template>

<script>
import GreetMe from './components/Greet.vue'

export default {
  name: 'App',
  components: {
    GreetMe
  },
  data() {
    return {
      name: 'milosh',
      email: 'milosh@gmail.com'
    }
  }
}
</script>

<style></style>
