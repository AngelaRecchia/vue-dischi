<template>
  <header class="w-100 d-flex align-items-center">
    <img src="../assets/logo.png" alt="logo spotify" class="ms-3" />
  </header>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style lang="scss" scoped>
@import "@/style/commons.scss";
header {
  height: 50px;
  background-color: #2e3a46;
  img {
    width: 30px;
  }
}
</style>
