<template>
  <div class="main">
    <div class="container">
      <ProductCard v-for="product in products" :product="product" :key="product.id" @delete="handleDelete"/>
    </div>
  </div>
</template>
<script>
import ProductCard from '@/components/product_card'
import data from '@/static/data.js'
export default {
  components: {
    ProductCard
  },
  data () {
    return {
      products: data
    }
  },
  methods: {
    handleDelete(value) {
      this.products = this.products.filter(el => el.id !== value)
    }
  }
}
</script>
<style scoped>
.container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  /*justify-content: space-between;*/
  gap: 16px 16px;
}
</style>
