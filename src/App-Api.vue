<template>
    <h2>This is Post Api</h2>
    <form @submit.prevent="formSubmit">
      <div>
        <label for="userId">User Id</label>
        <input type="text" id="userId" v-model="postData.UserID">
      </div>
      <div>
        <label for="title">Title:</label>
        <input type="text" id="title" v-model="postData.title">
      </div>
      <div>
        <label for="body" >Body:</label>
        <input type="text" id="body" v-model="postData.body">
      </div>
      <button>Create Post</button>
    </form>


<!--<h2>This is Fetch Api </h2>-->
<!--  <button @click="getPosts">Click to Button Show Data</button>-->
<!--    <div v-for="p in post" :key="p.id">-->
<!--      <h3>This is id : {{p.id}}</h3>-->
<!--      <h4>This is title : {{p.title}}</h4>-->
<!--      <h5>This is body : {{p.body}}</h5>-->
<!--    </div>-->



<!--  <h2>This is For PUT Api</h2>-->
<!--  <form @submit.prevent="updatePost">-->
<!--    <button>Update a post</button>-->
<!--  </form>-->


<!--  <h2>This is PATCH Api</h2>-->
<!--  <form @submit.prevent="patchData">-->
<!--    <button>Update a Single Dataset</button>-->
<!--  </form>-->

<!--  <h2>This is Delete Api</h2>-->
<!--    <form @submit.prevent="deleteData">-->
<!--      <button>Delete Data</button>-->
<!--    </form>-->
</template>

<script>
export default {
  // /* Post Api Start
    data(){
      return{ postData: {UserID:'',title:'',body:''}}
    },
  methods:{
      formSubmit(){
        fetch('https://jsonplaceholder.typicode.com/posts/',{
          method :'POST',headers:{
            'content-Type':'application/json'
          },
          body: JSON.stringify({
            userId: this.userId,
            title:this.title,
            body:this.body,
          })
        })
        .then(response =>response.json())
        .then(data =>console.log(data))
      }
  }
  // Post Api End */

  /* Fetch Api Start
  // data(){
  //   return{
  //     post:[]
  //   }
  // },
  // methods:{
  //   This is Fetch Api
  //   getPosts(){
  //     fetch('https://jsonplaceholder.typicode.com/posts/')
  //     .then(respnse =>respnse.json())
  //     .then (data =>this.post=data)
  //   }
  // },
  // mounted() {
  //   this.getPosts()     //This is Use for the mounted(Data already Print) all data when page is reload.
  // }

   Fetch Api End */

//  Put Api Start PUT(Entire Dataset Update)
//   methods:{
//     updatePost(){
//       fetch('https://jsonplaceholder.typicode.com/posts/1',{
//         method:'PUT',
//         headers:{
//           'Content-Type':'application/json',
//         },
//         body: JSON.stringify({
//             userId:1,
//             tile:'Updated Title',
//             body:'Updated Body',
//         })
//       })
//       .then(response =>response.json())
//       .then(data =>console.log(data))
//     }
//   }
//  Put Api End


  //Patch Api Start  PATCH(Each Dataset Update)
  // methods:{
  //   patchData(){
  //     fetch('https://jsonplaceholder.typicode.com/posts/1',{
  //       method:'PATCH',
  //       headers:{
  //         'Content-Type': 'application/json',
  //       },
  //       body:JSON.stringify({
  //         title:'This is Patch Update',
  //       })
  //     })
  //     .then(response =>response.json())
  //     .then(data =>console.log(data))
  //   }
  // }
//  Patch Api End

  //Delete Api Start
  // methods:{
  //   deleteData(){
  //     fetch('https://jsonplaceholder.typicode.com/posts/1',{
  //       method:'DELETE',
  //     })
  //     .then(response =>response.json())
  //     .then(data =>console.log(data))
  //   }
  // }
//  Delete Api End
}

</script>

<style>

</style>