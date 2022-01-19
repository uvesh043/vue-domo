<template>
  <div class="nav">
    <div class="header">
      <div class="linkDiv"><a href="#">Home</a></div>
      <div class="linkDiv"><a href="#"> About Us</a></div>
      <div class="linkDiv"><a href="#"> Services</a></div>
      <div class="linkDiv"><a href="#"> Contact Us</a></div>
      <div class="linkDiv"><a href="#"> Customer Review</a></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style>
.nav {
  /* border: 1px solid red; */
  width: 100vw;
  display: flex;
  background-color: rgb(94, 94, 226);
  color: white;
  justify-content: center;
}
.header {
  border: 1px solid rgb(255, 18, 148);
  display: flex;
  justify-content: space-around;
  width: 90vw;
}
.nav a {
  text-decoration: none;
  font-size: 1.5rem;
  background-color: #095bb4;
  color: white;
}
.linkDiv:hover {
  color: white;
  background-color: #940202;
}
</style>