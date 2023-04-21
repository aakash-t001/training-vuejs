<template>
<h1>This Is First Component</h1>
  <hr>
  <FirstCompA/>
</template>

<script>
import FirstCompA from './FirstCompA'
export  default{
  components: { FirstCompA }
}
</script>

<style scoped>
h1{
  color: red;
}
</style>