<template>
  <div id="app" class="text-center">
    <h1>Word Translator</h1>
    <h5>Powered by Vue.js</h5>
    <translate-form v-on:formSubmit="translateText"></translate-form>
    <translate-output v-text="translatedText"></translate-output>
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm'
import TranslateOutput from './components/TranslateOutput'

export default {
  name: 'App',
  components: {
    TranslateForm,
    TranslateOutput
  },
  data: function () {
    return {
      translatedText: ''
    }
  },
  methods: {
    translateText: function (text, language) {
      this.$http.get(`https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20181009T162704Z.80edfd10041c9342.892f1476cdef95a09af19e0ca58ab194a3bedf33&lang=${language}&text=${text}`)
        .then((response) => {
          this.translatedText = response.body.text[0]
        })
    }
  }
}
</script>

<style>
  body {
    background: #fefefe;
  }
</style>
