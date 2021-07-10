<template>
  <div id="app">
    <Header :albums="albums" @emitToApp="getGenreToShow" />
    <Content :albums="albumsToShow" />
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
      genreToShow: "All Genres",
      loading: true,
    };
  },
  created() {
    this.getAlbums();
  },
  methods: {
    getAlbums() {
      axios.get(this.urlAPI).then((result) => {
        this.albums = result.data.response.sort((a, b) => a.year - b.year);
      });
      this.loading = false;
    },
    getGenreToShow(genre) {
      this.genreToShow = genre;
    },
  },
  computed: {
    albumsToShow() {
      if (this.genreToShow == "All Genres") {
        return this.albums;
      } else
        return this.albums.filter((album) => album.genre == this.genreToShow);
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
