<template>
  
  <ComponentC />

</template>

<script>

import ComponentC from './components/ComponentC.vue';

export default {
  name: 'App',
  data() {
    return {

    }
  },
  components: {
    ComponentC
  },
  provide:{
    username: 'Milan'
  }
}
</script>

<style></style>
