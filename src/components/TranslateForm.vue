<template>
  <div id="translateForm">
    <div class="col-md-6 col-md-offset-3">
        <form id="transform" class="form-inline well" v-on:submit="formSubmit">
            <input class="form-control" type="text" v-model="textToTranslate" placeholder="Enter a word">
            <select class="form-control" v-model="language">
                <option value="es">Spanish</option>
                <option value="zh">Chinese</option>
                <option value="pl">Polish</option>                        
            </select>
            <br></br>
            <input class="btn btn-success" type="submit" value="Translate">
        </form>
    </div>
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
  created() {
        this.language = "es"; 
  },
  methods: {
      formSubmit(e) {
          this.$emit('formSubmit', this.textToTranslate, this.language); 
          e.preventDefault();
      }
  }
}
</script>

<style>
#transform {
    border: 2px #ccc solid; 
    border-radius: 10px; 
}
</style>