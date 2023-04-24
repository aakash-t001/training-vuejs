<template>
<!--  <h3>Hello My First Name is {{firstname}} and last name is {{lastname}}</h3>-->
  <h2>My Full Name is {{fullname}}</h2>
  <p>{{userName}}</p>
</template>

<script>
export  default {
  inject:['userName'],
  // props:['firstname','lastname','fullname']
  props:{
    // fullname:String,      //Code Works And run it shows waring if string not pass
    fullname:{
      type:String,
      required:true,
      default:'this is default mssg',    //this is only when work tha no props pass in parent compo if attribute is present but value null then this case this will not show
    }
  }
}
</script>

<style>

</style>