<template>
  <h2>It is Dynamic Component A</h2>
  <p>Name: {{name}}</p>
  <input type="text" v-model="name">
</template>
<script>
export  default {
  data(){
    return{
      name:'',
    }
  }
}

</script>

<style>

</style>