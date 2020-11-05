<template>
  <div>
    <select id="dropdown" @change="$emit('change-filter', filters)">
      <option v-bind:Titel="filters" value="Title">Titel</option>
      <option v-bind:Artist="filters">Artist</option>
      <option v-bind:YearOfProduction="filters">Year of Production</option>
      <option v-bind:Album="filters">Album</option>
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
