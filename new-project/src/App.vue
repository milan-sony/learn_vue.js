<template>

  <button @click="showPopup = true">show popup</button>
  <PopUp v-show="showPopup" @close="showPopup = false" />

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
  components:{
    PopUp
  }
}
</script>

<style></style>
