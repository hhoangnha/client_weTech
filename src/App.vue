<template>
  <div id="app">
    <input v-model="username" type="text" />
    <input v-model="password" type="password" />
    <button type="button" @click="login" class="btn btn-success">Login</button>
  </div>
</template>

<script>
import 'bootstrap/dist/css/bootstrap.min.css'
import axios from 'axios'
export default {
  name: 'app',
  data () {
    return {
      user:{
        username:"",
        password:"",
      }
    }
  },
  methods:{
    login(){
      axios.get('/user?ID=12345')
        .then(function (response) {
          alert(response.data.msg);
        })
        .catch(function (error) {
          // handle error
          console.log(error);
        })
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

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
