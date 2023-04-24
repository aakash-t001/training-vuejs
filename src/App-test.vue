<template>
  <button @click="showChild =!showChild">Toggle Child Component</button>
  <life-cycle-comp v-if="showChild"/>
<!--  /*This is Dyanmic Component-->
<!--  <p>-->
<!--    <button @click="activeComp='dynamic-comp'">Dynamic Comp</button>-->
<!--    <button @click="activeComp='dynamic-comp-a'">Dynamic Comp A</button>-->
<!--    <button @click="activeComp='dynamic-comp-b'">Dynamic Comp B</button>-->
<!--  </p>-->
<!--&lt;!&ndash;  Keep Alive is use for the when change the componant then not move the data&ndash;&gt;-->
<!--  <keep-alive>-->
<!--    <component :is="activeComp"/>-->
<!--  </keep-alive>-->
<!--  <DynamicComp v-if="activeComp ==='DynamicComp'"/>-->
<!--  <DynamicCompA v-if="activeComp==='DynamicCompA'"/>           this is check for a button click                                                                     which one is enable component-->
<!--  <DynamicCompB v-if="activeComp==='DynamicCompB'"/>-->

<!--  */-->
<!--  <custom-comp v-model="name"/>-->
<!--  <p>Name: {{name}}</p>-->
<!--  <button @click="isMenuOpen =true ">Open Now</button>-->
<!--  <event-comp v-if="isMenuOpen" @closeMenu="isMenuOpen =false"/>-->
<!--  <event-comp v-if="isMenuOpen" @closeMenu="closeMenu"/>-->
<!--  this is use for the who user close the menu and show user name get name using emit-->
<!--  <p>{{name}}</p>-->
<!--  <child-comp />-->
<!--  <first-comp-a/>-->
<!--  <child-comp firstname="Aman" lastname="Kumar"/>-->
<!--  <child-comp :firstname="fname" :lastname="lname"/>-->
<!--  <child-comp :fullname="fullname"/>-->
<!--  <child-comp first-name="Rohan" last-name="Pal"/>-->
<!--  <child-comp first-name="Sohan" last-name="Sharma"/>-->

</template>

<script>
// import ChildComp from "@/components/ChildComp";
// import FirstCompA from "@/components/FirstCompA";
// import EventComp from "@/components/EventMainComp";
// import CustomComp from "@/components/CustomComp";
// import DynamicComp from "@/components/DynamicComp";
// import DynamicCompA from "@/components/DynamicCompA";
// import DynamicCompB from "@/components/DynamicCompB";
import LifeCycleComp from "@/components/LifeCycleComp";
export  default{
  components: {LifeCycleComp},
  data(){
    return{
    showChild:false
    }
  },
  beforeCreate() {console.log('parent before create()')},
  created() {console.log('parent create()')},
  beforeMount() {console.log('parent before mount()')},
  mounted() {console.log('parent mounted()')},
  beforeUpdate() {console.log('parent before update()')},
  updated() {console.log('parent Updated()')},


  /*
// components:{DynamicComp,DynamicCompA,DynamicCompB},
//   data(){
//     return{
//       activeComp:'dynamic-comp'
//     }
//   }
  */



  /*
  // components: {CustomComp},
  // data(){                      it use for the custom component for use v bind to another componont
  //   return{
  //     name:''
  //   }
  // }


  /*
  // components:{EventComp},
  // data(){              This is use for button show and hide
  //   return {
  //     name:'',
  //     isMenuOpen: false
  //   }
  // },
  // methods:{                //this method is use for get name in menu close button
  //   closeMenu(data){
  //     this.isMenuOpen=false
  //     this.name=data
  //   }
  // }
  */



  /*
  // components:{FirstCompA, ChildComp},
  // provide:{                   //this is use for the directly inject the data who can provide main compo.
  //   userName:'Aash'
  // }
  */


  /*
  // data(){
  //   return {userName: 'Aash'}
  // },                             Provided data in same comp.but vue not allow to inject the same                                       comp data into the same comp. Then provide a data to data propety                                     then provide option to a object with the data property
  // provide(){
  //   return {userName: this.userName}
  // }
   */



  // data(){
  //   return{
  //     fname:'raman',
  //     lname:'singh'
  //   }
  // },
  // computed:{
  //   fullname(){
  //     return this.fname + ' ' +this.lname
  //   }
  // }
}


</script>

<style>

</style>