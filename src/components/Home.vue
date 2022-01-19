<template class="container">
<Header/>
<div class="imgDiv">
<!-- <img class="img" src="../assets/homePlumbingPic"> -->


</div>
<Footer/>
</template>
<style>
.imgDiv{
    width: 100vw;
    height: 50vh;
    background-color: violet;
     border: 1px solid rgb(27, 49, 29);
}
.img{
    border: 1px solid red;
}
</style>

<script>
import Header from "./Header.vue";
import Footer from "./Footer.vue";
export default {
    name:"Home",
    components:{
        Header,
        Footer
    },
     mounted() {
    console.log(localStorage.getItem("user"))
    let user = localStorage.getItem("user");
    if (!user) {
      this.$router.push({ name: "SignUp" });
    }
  },
}
</script>


