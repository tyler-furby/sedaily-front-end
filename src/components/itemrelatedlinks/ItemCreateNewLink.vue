<template>
  <div>
    <button v-on:click="openForm" v-show="!isCreating">
      +
    </button>
    <div v-show="isCreating">
      <label>URL</label>
      <input v-model="urlText" type='text' ref='title' defaultValue="">
    </div>
    <button class='ui basic blue button' v-show="isCreating" v-on:click="sendForm()">
      Add Link
    </button>
  </div>
</template>

<script>
export default {
  data () {
    return {
      urlText: '',
      isCreating: false
    }
  },
  methods: {
    openForm () {
      this.isCreating = true
    },
    closeForm () {
      this.isCreating = false
    },
    sendForm () {
      const title = this.titleText
      console.log(title)
      this.urlText = ''
      this.isCreating = false
    }
  }
}
</script>
