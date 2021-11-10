<template>
  <div class="product-list">
    <select v-model="selected" class="product-list__filter">
      <option disabled value="">По умолчанию</option>
      <option value="price min">По цене min</option>
      <option value="price max">По цене max</option>
      <option value="name">По наименованию</option>
    </select>
    <div class="product-list__container">
      <ProductCard v-for="product in sortedArray" :product="product" :key="product.id" @delete="handleDelete"/>
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
      products: [],
      selected: ''
    }
  },
  methods: {
    handleDelete(value) {
      this.products = this.products.filter(el => el.id !== value)
      localStorage.setItem('products', JSON.stringify(this.products))
    },
    parsePrice(n) {
      return parseInt(n.replace(/ /g, ''));
    }
  },
  computed: {
    sortedArray () {
      let tempArray = this.products;
      tempArray = tempArray.sort((a, b) => {
        if (this.selected === 'name') {
          if(a.name < b.name) return -1;
          if(a.name > b.name) return 1;
          return 0;
        }
        if(this.selected === 'price max') {
            return this.parsePrice(b.price) - this.parsePrice(a.price);
          }
        if(this.selected === 'price min') {
            return this.parsePrice(a.price) - this.parsePrice(b.price);
          }
      })
      return tempArray;
    }
  },
  mounted() {
    this.products = JSON.parse(localStorage.getItem('products'))
  }
}
</script>
<style scoped lang="scss">
@import "assets/variables.scss";

.product-list {
  display: flex;
  flex-direction: column;
  align-items: end;
}
.product-list__filter {
  width: 121px;
  height: 36px;
  color: $gray_2;
  box-shadow: $box-shadow;
  border: none;
  border-radius: $border-radiusS;
  margin-bottom: 16px;
}
.product-list__container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  gap: 16px 16px;
}
</style>
