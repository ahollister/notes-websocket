<template>
  <div class="container">
    <h2>{{ title }}</h2>
    <div class="card">
      <textarea name="messagebox"
                class="messagebox"
                maxlength="500"
                v-bind:placeholder="placeholder"
                v-model="message">
        {{message}}
      </textarea>
      <button href="#" v-on:click="submit">Submit</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: ''
    }
  },
  name: 'messagebox',
  props: ['title', 'placeholder'],
  methods: {
    submit: function() {
      if (this.message.length) {
        this.$emit('submit', this.message)
      }
      this.message = ''
    }
  }
}
</script>

<style scoped>
.card {
  text-align: right;
}
</style>
