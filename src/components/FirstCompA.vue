<template>
  <h2>This is First Component child component</h2>
  <p>{{userName}}</p>
</template>
<script>
export  default{
  inject:['userName']
}
</script>
