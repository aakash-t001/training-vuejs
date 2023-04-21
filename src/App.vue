<template>
  <button v-on:click="changeName('webreinvent company')">
    Click here to change name
  </button>
  <h1>
    This is first vue page {{name}}
  </h1>
  <h2>
    My name is {{userObj.fname}} {{userObj.lname}}
  </h2>
  <h2>
    My Designation is {{userArr['0']}} {{userArr['1']}}
  </h2>
  <a v-bind:href="link">
    Click here to redirect company website
  </a>
  <br/>
  <br/>
  <button :disabled="isDisabled">
    Boolean Attribute Binding
  </button>
  <p v-html="msgHtml">
  </p>
  <h2 v-pre>
    My name is {{userObj.fname}} {{userObj.lname}}
  </h2>
  <h3>
    Welcome mssg {{welcome()}}
  </h3>
  <input type="text" @input="getInput ($event,'fixedmssg')"/>
  <p>
    {{input}}
  </p>
  <button @click="increment">
    Increment Count Number
  </button>&nbsp;
  <button @click.right="increment">
    Right Click to Increment
  </button>
  <br/>
  <br/>
  <button @click="decrement">
    Decrement Count Number
  </button>
  <h2 v-once>
    Inital Counter Number is {{countnumber}}
  </h2>
  <h2>
    {{countnumber}}
  </h2>
  <form @submit="submitForm">
    <button>Submit button</button>
  </form>
  <input type="text" @keyup.enter="getFillInput">
  <p>
    {{input}}
  </p>
  <input type="text" v-model="twowaybind">
  <p>{{twowaybind}}</p>
  <label><input type="checkbox" value="Anmial" v-model="category">Animal</label>
  <label><input type="checkbox" value="Birds" v-model="category">Birds</label>
  <p>Selected Checkboxes {{category.join(',')}}</p>
  <select multiple v-model="country">
    <option value="India">India</option>
    <option value="US">US</option>
    <option value="China">China</option>
  </select>
  <p>Selectd Country {{country.join(',')}}</p>
  <form @submit.prevent="submissionForm">
    <label>Enter Your Name</label>
    <input type="text" id="name" v-model.lazy.trim="formData.name">
    <label>Enter Designation</label>
    <input type="text" id="designation" v-model.lazy.trim="formData.designation">
    <button>Submit Form</button>
  </form>
  <h3>Form Value of name {{formData.name}}  {{formData.designation}} </h3>
  <h3>Your City And Location {{address}}</h3>
</template>
<script>
export default {
  data(){
    return{
      name: "webreinvent",
      userObj:{fname:'Aakash',lname:'Tomer'},
      userArr:['Software','Developer'],
      link:'https://webreinvent.com/',
      isDisabled:false,
      msgHtml:'<h3>This is html</h3>',
      input:'',
      countnumber:20,
      twowaybind:'',
      category:[],
      country:[],
      city:'ghaziabad',
      location:'lal kuan',
      formData:{
        name:'',
        designation:''
      }
    }
  },
  computed:{
  address:{
    get(){
      return this.city + ' ' +this.location
    },
    set(values){
      const names=values.split(' ')
      this.city=names[0],
          this.location=names[1]
    }
  }
  },
  mounted() {
    this.address='Delhi Dwarka'
  },
  methods:{
    welcome(){
      return 'welcome to ' + this.name
    },
    changeName(name){
      this.name= name
    },
    getInput(event,lastfixedmsssg){
      this.input=event.target.value + ' ' + lastfixedmsssg
    },
    increment(){
      this.countnumber++
    },
    decrement(){
      this.countnumber--
    },
    submitForm(){
      event.preventDefault()
      console.log('form has been submitted');
    },
    getFillInput(event){
      this.input=event.target.value
    },
    submissionForm(){
      console.log('The Form Data is',this.formData)

    }


  }
}
</script>
<style scoped>
h1{
  color:green
}
</style>