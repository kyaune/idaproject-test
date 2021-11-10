<template>
  <div class="icon" @click="handleDelete">
    <img src="~/assets/delete1.png" alt="delete-icon" class="icon__img">
  </div>
</template>
<script>
export default {
  methods: {
    handleDelete() {
      this.$emit('handleDelete')
    }
  }
}
</script>
<style lang="scss" scoped>
@import "assets/variables.scss";
.icon {
  width: 32px;
  height: 32px;
  background-color: $red;
  border-radius: $border_radiusM;
}
.icon__img {
  width: 16px;
  height: 16px;
  position: absolute;
  top: 25%;
  left: 25%;
}
</style>
