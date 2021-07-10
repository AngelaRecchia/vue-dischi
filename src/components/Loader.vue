<template>
  <div class="text-center">
    <i class="fas fa-circle-notch"></i>
  </div>
</template>

<script>
export default {
  name: "Loader",
};
</script>

<style lang="scss" scoped>
div {
  font-size: 50px;
  color: #18d860;
  i {
    animation: spin 1s linear infinite;
    @keyframes spin {
      from {
        transform: rotate(0deg);
      }
      to {
        transform: rotate(360deg);
      }
    }
  }
}
</style>
