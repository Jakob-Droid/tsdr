<template>
  <div>
    <div>
      <Header @change-filter="searched(filters)" />
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
  methods: {
    searched: function(filters: string) {
      console.log("FUCK THIS SHIT IT FUCKING DOESN'T WORK! " + filters);
    },
  },
  computed: {},
})
export default class App extends Vue {}
</script>
