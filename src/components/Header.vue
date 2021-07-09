<template>
  <header class="w-100 d-flex align-items-center justify-content-between px-3">
    <img src="../assets/logo.png" alt="logo spotify" />
    <Select :albums="albums" />
  </header>
</template>

<script>
import Select from "./Select.vue";
export default {
  components: { Select },
  name: "Header",
  props: ["albums"],
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
