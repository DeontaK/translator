<template>
  <div id="app">
    <h1>Word Translator</h1>
    <h5>Powered by Vue.js</h5>
    <translate-form v-on:formSubmit="translateText"></translate-form>
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm'

export default {
  name: 'App',
  components: {
    TranslateForm
  },
  methods: {
    translateText: function (text) {
      
    }
  }
}
</script>

<style>

</style>
