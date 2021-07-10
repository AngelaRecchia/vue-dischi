<template>
  <main>
    <section
      v-if="!loading"
      class="
        w-75
        m-auto
        row row-cols-1 row-cols-sm-2 row-cols-md-4 row-cols-lg-5
        gy-3
      "
    >
      <div v-for="(album, index) in albums" :key="index" class="col">
        <Album :details="album" />
      </div>
    </section>
    <Loader v-else />
  </main>
</template>

<script>
import Album from "./Album.vue";
import Loader from "./Loader.vue";
export default {
  name: "Content",
  components: {
    Album,
    Loader,
  },
  props: ["albums", "loading"],
};
</script>

<style lang="scss" scoped>
@import "@/style/commons.scss";
main {
  background-color: #1e2d3b;
  padding: 30px 0;
  min-height: calc(100vh - 50px);
}
</style>
