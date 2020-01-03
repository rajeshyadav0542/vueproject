<template>
  <div class="hello">
    <p>
       ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
      tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
      quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
      consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
      cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
      proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
      <br>
      <br>
      ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
      tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
      quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
      consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
      cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
      proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

    </p>
     <div id='login'>
       Firstname : <input type="text" v-model="firstname" ></br></br>
       Lastname : <input type="text" v-model="lastname" ></br>
       <h1>My name is {{ firstname}} {{ lastname }}</h1>
       <h1>Using computed method : {{getfullname}}</h1>
    </div>
  </div>
  
</template>

<script>
export default {
  name: 'HelloWorld',
  props :{
    firstname : String,
    lastname : String
  }, 
  data : function(){
    return {
      msg : "Test for home page",    
    }
  },
  computed :{
      getfullname : function(){
        var first = this.firstname ? this.firstname : '';
        var last = this.lastname ? this.lastname : '';
         return first +" "+ last;
      }
   }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
