<template>
    <button class="button" :class="{active}">Добавление товара</button>
</template>
<script>
export default {
  props: {
    active: Boolean
  },
  mounted() {
    console.log(this.active)
  }
}
</script>
<style scoped lang="scss">
@import "assets/variables";
.button {
  width: 284px;
  font-size: $fontS;
  font-weight: 600;
  height: 36px;
  border: none;
  border-radius: $border_radiusM;
  background-color: $gray_1;
  color: $gray_2;
  margin-top: 16px;
  margin-left: 8px;
}
.active {
  background-color: $green;
  color: white;
}
</style>
