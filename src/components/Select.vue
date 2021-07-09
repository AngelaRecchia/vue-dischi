<template>
  <select class="form-select-sm" aria-label="Default select example">
    <option selected value="all">All Genres</option>
    <option v-for="(genre, index) in genres" :key="index" value="genre">
      {{ genre }}
    </option>
  </select>
</template>

<script>
export default {
  name: "Select",
  props: ["albums"],
  data() {
    return {
      genres: [],
    };
  },
  created() {
    for (const elem of this.albums) {
      if (!this.genres.includes(elem.genre)) {
        this.genres.push(elem.genre);
      }
    }
  },
};
</script>

<style lang="scss" scoped></style>
