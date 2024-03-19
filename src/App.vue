<template>

  <pre>
    {{ JSON.stringify(formValue, null, 2) }}
  </pre>

  <form>

    <div>
      <label for="name">Name</label>
      <input type="text" id="name" v-model="formValue.name">
    </div>

  </form>

</template>

<script>

export default {
  name: "App",
  data() {
    return {
      formValue:{
        name: ''
      }
    }
  },
  methods:{

  }
}

</script>

<style></style>
