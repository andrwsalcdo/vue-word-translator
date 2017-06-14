<template>
  <div id="app">
    <h1>Word Translator with Yandex</h1>
    <h5>By Vue.js</h5>
    <TranslateForm v-on:formSubmit="translateText"></TranslateForm>
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm'

export default {
  name: 'app', 
  components: {
    TranslateForm
  }, 
  methods: {
    translateText: function(text) {
      
    }
  }
}
</script>

<style>

</style>
