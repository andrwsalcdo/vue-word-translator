<template>
        <h2 class="col-sm-12 text-success">{{translatedText}}</h2>
</template>

<script>
export default {
  name: 'translateOutput',
  props:['translatedText']
}
</script>

<style>
h2 {
    font-size: 50px; 
}
</style>
