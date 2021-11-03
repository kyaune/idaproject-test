<template>
  <div>
    <DeleteIcon class="icon-container"/>
  <div class="card">
  <img src="~/assets/Rectangle31.jpg" alt="product image" class="product-image">
    <div class="container">
      <p class="product-name">Наименование товара</p>
      <p class="product-description">Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк</p>
      <p class="product-price">10 000 руб.</p>
    </div>
  </div>
  </div>
</template>
<script>
import DeleteIcon from '@/components/ui/delete_icon'
export default {
  components: {
    DeleteIcon
  }
}
</script>
<style lang="scss" scoped>
@import "assets/variables.scss";
.card {
  cursor: pointer;
  max-width: 332px;
  max-height: 423px;
  box-shadow: $box_shadow;
  border-radius: $border_radiusS;
  background-color: $white_1;
}
.icon-container {
  position: relative;
  left: calc(100% - 16px);
  top: 16px;
  max-width: 32px;
  max-height: 32px;
}
.product-image {
  max-width: 332px;
  max-height: 200px;
}
.container {
  padding: 16px 16px 24px 16px;
}
.product-name {
  font-size: $fontL;
  font-weight: 600;
}
.product-description {
  font-size: $fontM;
}
.product-price {
  font-size: $fontXL;
  font-weight: 600;
}
</style>
