<template>
  <select
    class="form-select-sm"
    aria-label="seleziona generi"
    v-model="selectedGenre"
    @change="$emit('emitGenre', selectedGenre)"
  >
    <option selected value="All Genres">All genres</option>
    <option v-for="(genre, index) in genres" :key="index" :value="genre">
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
      selectedGenre: "All Genres",
    };
  },
  computed: {
    genres() {
      let genres = [];
      for (const elem of this.albums) {
        if (!genres.includes(elem.genre)) {
          genres.push(elem.genre);
        }
      }
      return genres;
    },
  },
};
</script>

<style lang="scss" scoped></style>
