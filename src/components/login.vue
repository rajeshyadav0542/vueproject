<template>
    <div class="col-sm-4 col-sm-offset-4">
      <h2>Log In</h2>
      <p>Log in to your account to get some great quotes.</p>
      <div class="alert alert-danger" v-if="error">
        <p>{{ error }}</p>
      </div>
      <div class="form-group">
        <input type="text" class="form-control" placeholder="Enter your username" v-model="credentials.username" >
      </div></br>
      <div class="form-group">
        <input  type="password" class="form-control" placeholder="Enter your password" v-model="credentials.password">
      </div> </br>
        <button class="btn btn-primary" @click="submit()">Access</button>
    </div>
  </template>

  <script>
  import axios from 'axios'
  export default {
    data() {
      return {
        // We need to initialize the component with any
        // properties that will be used in it
        credentials: {
          username: '',
          password: ''
        },
        error: ''
      }
    },
    methods: {
      submit() {
        var body = {
          eamil: this.credentials.username,
          password: this.credentials.password
        }
        var header_token = { header : 'header' };
        var config = {
        headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
        responseType: 'blob'
      };

        fetch("http://192.168.1.250:3000/api/v1/user/login", { method: 'POST', headers: { 'Content-Type': 'application/json' }, body: JSON.stringify({ name: 'Hubot', login: 'hubot'}), config})
          .then(response => {
            cosole.log(response);
            if(response.status==500){
              alert(response.error);
            }else{
              console.log(response);
            }
          })
          .catch(e =>{
              console.log('Error : ', e);
          })
        } 
        // We need to pass the component's this context
        // to properly make use of http in the auth service
        //auth.login(this, credentials, 'secretquote')
    }

  }
  </script>