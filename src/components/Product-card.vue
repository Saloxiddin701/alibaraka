<template>
  <div class="card">
    <img :src="product.image ? product.image : default_image" :alt="product.name">
    <div class="text">
      <h1>{{ product.name }}</h1>
      <p>{{ product.text }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Product-card",
  props: {
    product: {
      type: Object,
      default: () => ({})
    }
  },
  data() {
    return {
      default_image: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRU2kVc1rpu0zFLcinUxktDvMW7xSnsFwo4jA&usqp=CAU'
    }
  }
}
</script>

<style scoped>

</style>