<template>
  <div class="text-center" id="app">
    <h1>Word Translator with Yandex</h1>
    <h5>Powered By Vue.js</h5>
    <hr>
    <TranslateForm v-on:formSubmit="translateText"></TranslateForm>
    <TranslateOutput v-text="translatedText"></TranslateOutput>
  </div>
</template>

<script>
import axios from 'axios'
import TranslateForm from './components/TranslateForm'
import TranslateOutput from './components/TranslateOutput'

export default {
  name: 'app',
  components:{
    TranslateForm,
    TranslateOutput
  },
  data: function(){
    return {
      translatedText:''
    }
  },
  methods: {
    translateText(text, language) {
      axios.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20170614T020251Z.d04903016ebe2c04.1f5b615b327860fde220d9ce388805c1a9008913&lang='+language+'&text='+text)
        .then(res => { this.translatedText = res.data.text[0]; })
        .catch(err => { console.log('This is wrong'); })
    }
  }
}
</script>

<style>
body {
  background: lightcoral; 
}
</style>
