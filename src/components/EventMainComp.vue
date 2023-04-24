<template>
  <h2>Main Menu Component</h2>
  <p><input type="text" v-model="name"></p>
  <button @click ="$emit('closeMenu',name)">Close the Menu</button>
</template>

<script>
export  default {
  emits: {
    closeMenu(name){         //This is use for the valdation
      if (!name)
      return false
      else
        return  true
    }
  },
  data(){
    return{
      name:'',
    }
  }
}
</script>

<style>

</style>