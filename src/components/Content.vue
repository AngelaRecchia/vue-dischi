<template>
  <main>
    <Album v-for="(album, index) in albums" :key="index" :details="album" />
  </main>
</template>

<script>
import axios from "axios";
import Album from "./Album.vue";
export default {
  name: "Content",
  components: {
    Album,
  },
  data() {
    return {
      urlAPI: "https://flynn.boolean.careers/exercises/api/array/music",
      albums: "",
      loading: true,
    };
  },
  created() {
    this.getAlbums();
  },
  methods: {
    getAlbums() {
      axios.get(this.urlAPI).then((result) => {
        this.albums = result.data.response;
      });
    },
  },
};
</script>

<style lang="scss" scoped>
@import "@/style/commons.scss";
main {
  height: calc(100vh - 50px);
  background-color: #1e2d3b;
}
</style>
