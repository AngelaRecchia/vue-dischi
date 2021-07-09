<template>
  <div id="app">
    <Header :albums="albums" />
    <Content :albums="albums" />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Content from "./components/Content.vue";
import axios from "axios";
export default {
  name: "App",
  data() {
    return {
      urlAPI: "https://flynn.boolean.careers/exercises/api/array/music",
      albums: "",
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
  components: {
    Header,
    Content,
  },
};
</script>

<style lang="scss">
@import "@/style/commons.scss";
</style>
