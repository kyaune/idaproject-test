<template>
  <div class="main" @click="handleDelete">
    <img src="~/assets/delete1.png" alt="delete-icon" class="icon">
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
.main {
  width: 32px;
  height: 32px;
  background-color: $red;
  border-radius: $border_radiusM;
}
.icon {
  width: 16px;
  height: 16px;
  position: absolute;
  top: 25%;
  left: 25%;
}
</style>
