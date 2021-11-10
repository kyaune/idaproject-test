<template>
  <div class="main">
    <Sidemenu></Sidemenu>
    <ProductsList></ProductsList>
  </div>
</template>

<script>
import Sidemenu from '@/components/sidemenu'
import ProductsList from '@/components/products_list'
import data from '@/static/data'
export default {
  components: {
    Sidemenu,
    ProductsList
  },
  created() {
    if(!localStorage.getItem('products')) {
      localStorage.setItem('products', JSON.stringify(data))
    }
  }
}
</script>
<style scoped lang="scss">
@import "assets/variables";
 .main {
   display: flex;
   flex-direction: row;
   font-family: 'Source Sans Pro', sans-serif;
   padding: 32px;
   gap: 16px;
 }
</style>
