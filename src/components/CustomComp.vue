<template>
<h2>This is Custom Template using bind input field (Because V model directive not a behave custom component</h2>
  <input type="text" :value="modelValue" @input="$emit('update:modelValue',$event.target.value)">
</template>

<script>
export  default {
  props:{
    modelValue:String
  }
}
</script>

<style>

</style>