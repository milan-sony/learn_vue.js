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
  <h1 v-bind:class="[isPromoted && 'promoted', isSoldout ? 'sold-out' : 'new']">Array condition movie</h1>
  <h1 v-bind:class="{
    // key : class name, value : condition
    promoted: isPromoted,
    new: !isSoldout,
    'sold-out': isSoldout
  }">Object condition movie</h1>


  <h2 v-bind:style="{
    // key : css property value : data property/condition
    color: highlightColor,
    'font-size': headerSize,
    'padding': '20px'
  }">Inline style</h2>

  <h2 v-bind:style="headerStyleObj">Style Object</h2>
  <h2 v-bind:style="[headerStyleObj, newStyleObj]">Style array object</h2>

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
      isPromoted: true,
      isSoldout: false,
      highlightColor: 'orange',
      headerSize: '50px',
      headerStyleObj: {
        color: 'Blue',
        'font-size' : '30px',
        padding: '10px'
      },
      newStyleObj:{
        'font-size': '40px',
        'background-color': 'yellow'
      }
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

.new {
  color: green;
}

.sold-out {
  color: red;
}
</style>
