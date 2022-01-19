<template class="container">
  <img class="logo" alt="Vue logo" src="../assets/plumbing&heating.png" />
  <h1>Sign Up</h1>
  <div class="container">
    <input type="text" v-model="name" placeholder="Enter Name" />
    <input type="email" v-model="email" placeholder="Enter Email" />
    <input type="password" v-model="password" placeholder="Enter Passsword" />
    <button @click="signUp">Sign Up</button>
    <div class="loginBtn">
<router-link to="/login">Alreeady Have Account</router-link>
      
  </div> 
  </div>
</template>

<script>
import axios from "axios";

// import VueToast from 'vue-toast-notification';
export default {
  name: "Signp",
  data() {
    return {
      name: "",
      email: "",
      password: "",
    };
  },
  methods: {
    async signUp() {
      if (!this.name || !this.email || !this.password) {
        console.log("Please fill the form first");
      }
      let result = await axios.post(" http://localhost:3000/users", {
        email: this.email,
        password: this.password,
        name: this.name,
      });
      console.warn(result);
      if (result.status == 201) {
        localStorage.setItem("user", JSON.stringify(result.data));
        this.$router.push({ name: "Home" });
      }
    },
  }
 
};
</script>

<style >

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