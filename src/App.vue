<template>

  <div>{{ greetings }}</div>
  <div v-text="name"></div>

  <div v-bind:id="headingId">Heading</div>
  <button v-bind:disabled="isDisabled">Button</button>

  <h1 class="underline">Text Underline</h1>
  <h1 v-bind:class="status">Text Underline</h1>
  <h1 class="underline" v-bind:class="status">Text Underline</h1>
  <h1 v-bind:class="isPromoted && 'promoted'">Promoted Movie</h1>
  <h1 v-bind:class="isSoldout ? 'sold-out' : 'new'">Sold out movie</h1>
  <h1 v-bind:class="['new', 'promoted']">New Movie</h1>

</template>

<script>

export default {
  name: "App",
  data() {
    return {
      greetings: "Hello",
      name: "MilanSony",
      headingId: 'ID',
      isDisabled: true,
      status: 'danger',
      isPromoted: false,
      isSoldout: true
    }
  }
}

</script>

<style>

.underline {
  text-decoration: underline;
}

.promoted {
  font-style: italic;
}

.new{
  color: green;
}

.sold-out{
  color: red;
}

</style>
