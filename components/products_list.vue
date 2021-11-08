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
  },
  data () {
    return {
      products: [
        {
          name: "namaman",
          description: "wqeeqweqwqweeqwqew",
          price: 12000,
          image: "https://s3-alpha-sig.figma.com/img/488b/7f1f/e88ef4c6003a678c0c9d6a1b91606ae9?Expires=1636934400&Signature=L5c5o~J0qKbs2OETmA~zvFWSsPQCCq5NmXTozFtHoHAReSS0soYltYY-smh3XZn4aRZFuRitHCz6sOnFR9lz3rC17ebDNQkFWoekE3Q2u6Srdh4TJUq-bRJ4hzMkw5c8KAMlj0r8bGGvj1APsoPMUaJxwuScaKdo0pAwZHWu2aNUOixMY8u5aofYQstg3068jPF1mLFByx0D2o93j~wPDl5irNZWUTmIfAVgzBxi-vOeltsCudsqwj0cOFAyjujdBuPct3gcE~95bwD892Am68Dch5jf9vk4XB03iynVlcOK9H3MlaKtXo1aE~xT0TPTpjFmtXV5AmIXfYFXf5-b2w__&Key-Pair-Id=APKAINTVSUGEWH5XD5UA"
        }
      ]
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
