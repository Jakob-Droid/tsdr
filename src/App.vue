<template>
  <div>
    <div>
      <Header v-on:change-filter="searched" />
    </div>
    <div>
      <div class="container">
        <RecordCard :records="records" />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import RecordCard from "./components/RecordCard.vue";
import Header from "./components/Header.vue";
import SearchBar from "./components/SearchBar.vue";

@Options({
  data: function() {
    return {
      records: Array,
    };
  },
  components: {
    RecordCard,
    Header,
    SearchBar,
  },
  mounted: function() {
    fetch("https://drmusicrestservice.azurewebsites.net/api/DRMusicRecord")
      .then((response) => response.json())
      .then((data) => {
        this.records = data;
      });
  },
  computed: {
    searched: function(name: any) {
      console.log("FUCK THIS SHIT IT FUCKING DOESN'T WORK!" + name[0]);
    },
  },
})
export default class App extends Vue {}
</script>
