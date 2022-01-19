<template class="container">
  <img class="logo" alt="Vue logo" src="../assets/plumbing&heating.png" />
  <h1>Login</h1>
  <div class="container">
    <input type="email" v-model="email" placeholder="Enter Email" />
    <input type="password" v-model="password" placeholder="Enter Passsword" />
    <button @click="login">Login</button>
    <div class="loginBtn">
      <router-link to="/sign-up">Create New Account</router-link>
    </div>
  </div>
</template>
<script>
import axios from "axios";
export default {
  name: "Login",
  data(){
   return{
        email: "",
    password: "",
   }
  },
  methods: {
  async  login() {
          let result=await axios.get(`http://localhost:3000/users?email=${this.email}&password=${this.password}`)
console.log(result)
if(result.status==200 && result.data.length>0)
   localStorage.setItem("user",JSON.stringify(result.data[0]))
   this.$router.push({name:"Home"})
    },
  },
  mounted(){
      let user=localStorage.getItem("user")
      if(user){
        this.$router.push({name:"Home"})
      }
      
  }
};
</script>
<style>
.loginBtn {
  border: 1px solid red;
}
.logo {
  width: 100px;
  border: 1px solid red;
}
.container {
  height: 50vh;
  border: 1px solid blue;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.container input {
  border: 1px solid red;
  margin-top: 10px;
  padding: 0.2rem;
  /* border: none; */
  outline: none;
  width: 300px;
  height: 40px;
  display: flex;
}
.container button {
  margin-top: 1rem;
  background-color: skyblue;
  border: 1px solid rgb(36, 138, 179);
  width: 320px;
  padding: 0.5rem;
}
</style>