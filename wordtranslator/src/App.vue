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
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20181009T162704Z.80edfd10041c9342.892f1476cdef95a09af19e0ca58ab194a3bedf33&lang=ru&text=' + text)
      .then((response) => {
        console.log(response)
      })
    }
  }
}
</script>

<style>

</style>
