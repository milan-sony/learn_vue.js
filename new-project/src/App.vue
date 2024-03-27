<template>

  <button @click="showPopup = true">show popup</button>
  <PopUp v-show="showPopup" @close="closePopup" />

</template>

<script>

import PopUp from './components/Popup.vue'

export default {
  name: 'App',
  data() {
    return {
      showPopup: false
    }
  },
  components: {
    PopUp
  },
  methods: {
    closePopup(name) {
      this.showPopup = false
      console.log('Name: ', name)
    }
  }
}
</script>

<style></style>
