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
  props: ['id'],
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
      const urlText = this.urlText
      console.log(this.id)
      console.log(urlText)

      this.$store.dispatch('addLink', {
        id: this.id,
        url: urlText
      })

      this.urlText = ''
      this.isCreating = false
    }
  }
}
</script>
