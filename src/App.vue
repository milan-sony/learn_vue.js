<template>

  <div>{{ greetings }}</div>
  <div v-text="name"></div>
  <div v-bind:id="headingId">Heading</div>
  <button v-bind:disabled="isDisabled">Button</button>

</template>

<script>

export default {
  name: "App",
  data(){
    return{
      greetings: "Hello",
      name: "MilanSony",
      headingId: 'ID',
      isDisabled: true
    }
  }
}

</script>

<style>

</style>
