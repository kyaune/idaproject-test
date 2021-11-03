<template>
  <div class="main">
    <Sidemenu></Sidemenu>
    <ProductsList></ProductsList>
  </div>
</template>

<script>
import Sidemenu from '@/components/sidemenu'
import ProductsList from '@/components/products_list'
export default {
  components: {
    Sidemenu,
    ProductsList
  }
}
</script>
<style scoped lang="scss">
@import "assets/variables";
 .main {
   display: flex;
   flex-direction: row;
 }
</style>
