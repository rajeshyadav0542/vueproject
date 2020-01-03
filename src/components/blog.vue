<template> 
  <div class="blog">  
      <h1>{{ title }}</h1>
     <ul>
          <li v-for="product in products">
            <input type="number" v-model.number="product.quantity">
             {{ product.name }}
            <span v-if="product.quantity===0">
              - OUT OF STOCK
            </span>
            <button @click="product.quantity +=1">Add</button>
          </li>
     </ul>
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
  </div>
</template>
<script> 
export default 
  {  
    name:'blog',  
    data (){   
      return {
        title : "Blog",
        products : []
      }
    },
     created(){
      fetch('http://192.168.1.250:3000/api/v1/product/all')
      .then(response => response.json())
      .then(json => {
        this.products = json.result
      })
    } 
  }
</script>

<style scoped> </style>
