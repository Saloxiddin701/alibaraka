<template>
  <Navbar/>
  <Home/>
  <Products/>
  <Clients/>
  <success/>
  <garden/>
  <Footer/>
</template>

<script>
import './assets/css/main.css'
import Home from "@/views/Home";
import Navbar from "@/components/Navbar";
import Products from "@/components/Products";
import Clients from "@/components/Clients";
import success from "@/components/Success";
import garden from "@/components/garden";
import Footer from "@/components/footer";

export default {
  name: 'App',
  components: {
    Navbar,
    Home,
    Products,
    Clients,
    success,
    garden,
    Footer
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  scroll-behavior: smooth;
}

.container {
  width: 85%;
  margin: 0 auto;
}
</style>
