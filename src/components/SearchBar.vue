<template>
  <div>
    <select
      v-model="filters"
      id="dropdown"
      @change="$emit('change-filter', filters)"
    >
      <option v-bind:Titel="filters" value="Title">Titel</option>
      <option v-bind:Artist="filters" value="Artist">Artist</option>
      <option v-bind:YearOfProduction="filters" value="YearOfProduction"
        >Year of Production</option
      >
      <option v-bind:Album="filters" value="Album">Album</option>
    </select>
  </div>
</template>
<script>
export default {
  name: "SearchBar",
  props: [],
  data: function() {
    return {
      filters: "",
      search: "",
    };
  },
  method: function() {
    return null;
  },
};
</script>

<style scoped>
#dropdown {
  max-width: 20vw;
  align-content: center;
}
</style>
