<template>
  <div class="sidemenu">
    <p class="header">Добавление товара</p>
    <div class="container">
      <form class="container__form" @submit="checkForm">
        <div class="container__element">
          <p class="container__description required">Наименование товара</p>
          <input type="text" v-model="name" name="name" placeholder="Введите наименование товара" class="container__input" :class="{ 'error': isClicked && !name}">
          <p class="container__error" v-if="isClicked && !name">Поле является обязательным</p>
        </div>
        <div class="container__element">
          <p class="container__description">Описание товара</p>
<!--         TODO: textarea placeholder doesnt match input placeholder-->
          <textarea v-model="description" placeholder="Введите описание товара" class="container__input" id="good-description"></textarea>
        </div>
        <div class="container__element">
          <p class="container__description required">Ссылка на изображение товара</p>
          <input type="text" name="image" v-model="image" placeholder="Введите ссылку" class="container__input" :class="{ 'error': isClicked && !image}" >
          <p class="container__error" v-if="isClicked && !image">Поле является обязательным</p>
        </div>
        <div class="container__element">
          <p class="container__description required">Цена товара</p>
          <input type="text" name="price" @blur="thousandsSeparator" v-model.number="price" placeholder="Введите цену" class="container__input" :class="{ 'error': isClicked && !price}">
          <p class="container__error" v-if="isClicked && !price">Поле является обязательным</p>
        </div>
        <input class="button" type="submit" :class="{'active' : name && price && image}" value="Добавить товара">
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      active: false,
      isClicked: false,
      name: null,
      price: null,
      description: null,
      image: null
    }
  },
  computed: {
    products() {
      return JSON.parse(localStorage.getItem('products'))
    }
  },
  methods: {
    checkForm() {
      this.isClicked = true;
      if(this.name && this.price && this.image) {
        this.active = false;
        this.isClicked = false;
        this.addProduct();
        return true;
      }
    },
    getNewId() {
      const products = JSON.parse(localStorage.getItem('products'))
      const lastIndex = products[products.length - 1].id
      return lastIndex + 1;
    },
    addProduct() {
      const newProduct = {name: this.name, description: this.description, price: this.price, id: this.getNewId(), image: this.image}
      this.products.push(newProduct)
      localStorage.setItem('products', JSON.stringify(this.products))
    },
    thousandsSeparator() {
      if (this.price !== '' || this.price !== undefined || this.price !== 0 || this.price !== '0' || this.price !== null) {
        this.price = this.price.toString().replace(/\B(?=(\d{3})+(?!\d))/g, " ");
      } else {
        return this.price;
      }
    }
  }
  // mounted() {
  //   this.products = JSON.parse(localStorage.getItem('products'))
  // }
}
</script>

<style scoped lang="scss">
@import "assets/variables";
p {
  margin: 0;
}
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
  font-family: 'Source Sans Pro', sans-serif;
  border: none;
  border-radius: $border_radiusS;
  box-shadow: $box-shadow;
  height: 36px;
  width: 100%;
  font-size: $fontS;
  padding: 0 0 0 16px;
}
.container__error {
  padding-top: 4px;
  color: $red;
  font-size: $fontXXS;
}
.error {
  border: 1px solid $red;
}
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
#good-description {
  height: 108px;
  resize: none;
  padding: 10px 0 0 16px;
}
textarea {
  background-color: $white_1;
}
textarea::placeholder {
  color: $gray_2;
}
input::placeholder {
  color: $gray_2;
  padding-top: 10px;
}
.required::after {
  content: " ●";
  color: $red;
}

</style>
