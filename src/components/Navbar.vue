<template>
  <div class="container">
    <nav class="navbar">
      <div class="logo">
        <img src="../assets/images/ali.png" alt=""/>
      </div>
      <ul class="list">
        <li><a href="">Products</a></li>
        <li><a href="">About Us</a></li>
        <li><a href="">Blog</a></li>
        <li><a href="">Contact</a></li>
      </ul>
      <div class="phone">
        <i class="fa fa-phone"></i>
        <div class="number">
          <h1>95-004-80-90</h1>
          <h1>94-641-40-00</h1>
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  name: "Navbar"
}
</script>

<style scoped lang="scss">
@import "../assets/css/navbar";
</style>