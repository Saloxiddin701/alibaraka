<template>
  <section class="products" id="product">
    <img src="../assets/images/product-bg.png" alt="" class="img">
    <div class="container">
      <div class="title">
        <h1>our production</h1>
        <p>
          "Your work is going to fill a large part of your life, and the only way to be truly satisfied is to do what
          you believe is great work]
        </p>
      </div>
      <div class="box">
        <ProductCard
          v-for="product in products"
          :key="product.id"
          :product="product"
        />
      </div>
      <div class="about">
        <div class="left">
          <h1>little ABout our company</h1>
          <p>
            "Your work is going to fill a large part of your life, and the only way to be truly satisfied is to do what
            you believe is great work. And the only way to do great work is to love what you do."
          </p>
          <div class="buttons">
            <button class="btn active">more about</button>
            <button class="btn">our youtube</button>
          </div>
        </div>
        <img src="../assets/images/cloud.png" alt="" class="cloud">
        <div class="right">
          <img src="../assets/images/tractor.png" alt="" class="tractor">
          <img src="../assets/images/left.png" alt="" class="img-left">
          <img src="../assets/images/right.png" alt="" class="img-right">
        </div>
      </div>
    </div>
    <div class="bottom">
      <div class="container">
        <div class="wrapper">
          <h4>Trusted <br> by</h4>
          <div class="item">
            <i class="fa fa-windows"></i> Microsoft
          </div>
          <div class="item">
            <h3>Google</h3>
          </div>
          <div class="item">
            <i class="fa fa-slack"></i> slack
          </div>
          <div class="item">
            <i class="fa fa-wordpress"></i> WordPress
          </div>
          <i class="fa fa-chevron-right"></i>
        </div>
        <img src="../assets/images/bottom-img-removebg-preview.png" alt="">
      </div>
    </div>
  </section>
</template>

<script>
import ProductCard from "@/components/Product-card";
import axios from 'axios'

export default {
  name: 'Products',
  components: {
    ProductCard
  },
  data() {
    return {
      products: [],
      api: 'https://alibaraka.pythonanywhere.com/api/products/'
    }
  },
  methods: {
    async fetchProducts() {
      const res = await axios.get(this.api)
      this.products = res.data
    }
  },
  mounted() {
    this.fetchProducts()
  }
}
</script>

<style scoped>
@import "../assets/css/product.scss";
</style>