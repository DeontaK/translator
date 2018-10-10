<template>
  <div id="translateForm" class="row">
    <div class="col-md-6 col-md-offset-3">
    <form v-on:submit="formSubmit" class="well form-inline" id="transForm">
      <input class="form-control" type="text" v-model="textToTranslate" placeholder="Enter a word...">
      <select class="form-control" v-model="language">
        <option value="ru">Russian</option>
        <option value="es">Spanish</option>
        <option value="fr">French</option>
        <option value="zh">Chinese</option>
      </select>
      <input class="btn btn-primary" type="submit" value="Translate">
    </form>
  </div>
  </div>
</template>

<script>
export default {
  name: 'translateForm',
  data () {
    return {
      textToTranslate: '',
      language: ''
    }
  },
  methods: {
    formSubmit (e) {
      this.$emit('formSubmit', this.textToTranslate, this.language)
      e.preventDefault()
    }
  },
  created () {
    this.language = 'ru'
  }
}
</script>

<style>
  #transForm {
    border-radius: 10px;
    border: 1px #ccc solid;
  }
</style>
