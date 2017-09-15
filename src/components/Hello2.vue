<template>
  <div>
    <h5>Hello {{name}}</h5>
    <input type="text" v-model="name">
  </div>
</template>
<script>
  export default {
    data () {
      return {
        name: 'Olga'
      }
    }
  }
</script>
<style scoped>
  h5 {
    color: #317a80;
    background: ghostwhite;
  }
</style>