<template>
  <div id="translateForm">
    <form v-on:submit="formSubmit">
        <input type="text" v-model="textToTranslate" placeholder="Enter a word">
        <select v-model="language">
            <option value="es">Spanish</option>
            <option value="zh">Chinese</option>
            <option value="pl">Polish</option>                        
        </select>
        <input type="submit" value="Translate">
    </form>
  </div>
</template>

<script>
export default {
  name: 'translateForm', 
  data() {
      return {
          textToTranslate: '',
          language: ''
      }
  }, 
  methods: {
      formSubmit(e) {
          this.$emit('formSubmit', this.textToTranslate); 
          e.preventDefault();
      }
  }
}
</script>

<style>

</style>
