<template>
  <div
  @mouseover="hover = true"
  @mouseout="hover = false"
  class="product"
  >
    <DeleteIcon v-show="hover" class="icon-container"/>
    <div class="product__card">
      <img src="~/assets/Rectangle31.jpg" alt="product image" class="product__image">
      <div class="product__container">
        <p class="product__name">Наименование товара</p>
        <p class="product__description">Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк</p>
        <p class="product__price">10 000 руб.</p>
      </div>
  </div>
  </div>
</template>
<script>
import DeleteIcon from '@/components/ui/delete_icon'
export default {
  components: {
    DeleteIcon
  },
  props: {
    product: Object
  },
  data() {
    return {
      hover: false
    }
  }
}
</script>
<style lang="scss" scoped>
@import "assets/variables.scss";
p {
  margin: 0;
}
.product {
  cursor: pointer;
  position: relative;
}
.product__card {
  max-width: 332px;
  max-height: 423px;
  box-shadow: $box_shadow;
  border-radius: $border_radiusS;
  background-color: $white_1;
}
.icon-container {
  position: absolute;
  left: calc(100% - 20px);
  top: -12px;
  max-width: 32px;
  max-height: 32px;
}
.product__image {
  max-width: 332px;
  max-height: 200px;
}
.product__container {
  padding: 16px 16px 24px 16px;
}
.product__name {
  font-size: $fontL;
  font-weight: 600;
}
.product__description {
  font-size: $fontM;
  padding: 16px 0 32px 0;
}
.product__price {
  font-size: $fontXL;
  font-weight: 600;
}
</style>
