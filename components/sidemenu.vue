<template>
  <div class="sidemenu">
    <p class="header">Добавление товара</p>
    <div class="container">
      <form class="container__form">
        <div class="container__element">
          <p class="container__description">Наименование товара</p>
          <input type="text" name="name" placeholder="Введите наименование товара" class="container__input">
        </div>
        <div class="container__element">
          <p class="container__description">Описание товара</p>
          <input type="textarea" name="name" placeholder="Введите описание товара" class="container__input">
        </div>
        <div class="container__element">
          <p class="container__description">Ссылка на изображение товара</p>
          <input type="text" name="name" placeholder="Введите ссылку" class="container__input">
        </div>
        <div class="container__element">
          <p class="container__description">Цена товара</p>
          <input type="text" name="name" placeholder="Введите цену" class="container__input">
        </div>
      </form>
      <Button></Button>
    </div>
  </div>
</template>

<script>
import Button from '@/components/ui/button'
export default {
  components: {
    Button
  }
}
</script>

<style scoped lang="scss">
@import "assets/variables";
.sidemenu {
  min-width: 332px;
  background-color: $white_1;
  display: flex;
  flex-direction: column;
}
.header {
  font-size: $fontXXL;
  font-weight: 600;
  line-height: 35px;
}
.container {
  box-shadow: 0 20px 30px rgba(0, 0, 0, 0.04), 0 6px 10px rgba(0, 0, 0, 0.02);
  border-radius: $border_radiusS;
  padding: 24px;
}
.container__form {
  display: flex;
  flex-direction: column;
}
.container__element {
  padding: 8px 0
}
.container__description {
  font-size: $fontXS;
  letter-spacing: -0.02em;
  line-height: 13px;
  margin: 0 0 4px 0;
}
.container__input {
  border-radius: $border_radiusS;
  box-shadow: $box-shadow;
  height: 36px;
  width: 100%;
  font-size: $fontS;
  color: $gray_2;
}

</style>
