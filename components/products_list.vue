<template>
  <div class="main">
    <div class="container">
      <ProductCard/>
      <ProductCard/>
      <ProductCard/>
      <ProductCard/>
      <ProductCard/>
      <ProductCard/>
    </div>
  </div>
</template>
<script>
import ProductCard from '@/components/product_card'
export default {
  components: {
    ProductCard
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
