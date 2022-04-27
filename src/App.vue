<template>
  <Navbar/>
  <router-view/>
  <Products/>
  <Clients/>
  <success/>
</template>

<script>
import Navbar from "@/components/Navbar";
import Products from "@/components/Products";
import Clients from "@/components/Clients";
import success from "@/components/Success";

export default {
  name: 'App',
  components: {
    Navbar,
    Products,
    Clients,
    success
  }
}
</script>

<style>
@import "assets/css/main.css";

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.container {
  width: 85%;
  margin: 0 auto;
}
</style>
