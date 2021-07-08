<template>
  <div class="box text-center">
    <img :src="details.poster" :alt="details.author" />
    <h6 class="author text-uppercase">{{ details.title }}</h6>
    <div class="infos">
      {{ details.author }}
      <br />
      {{ details.year }}
    </div>
  </div>
</template>

<script>
export default {
  name: "Album",
  props: ["details"],
};
</script>

<style lang="scss" scoped>
.box {
  background-color: #2e3a46;
  height: 300px;
  width: 150px;
  padding: 15px;
  margin: 10px 15px;
  img {
    width: 120px;
  }
  .author {
    color: white;
    margin-top: 20px;
  }
  .infos {
    color: #707983;
  }
}
</style>
