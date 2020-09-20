<template>
  <div class="search">
    <h2>SEARCH PICTURES ABOUT NASA</h2>
    <h1>(Search English only)</h1>
    <form v-on:submit.prevent="getResult(query)">
      <input type="text" size="30" placeholder=" SEARCH PICTURES ABOUT NASA" v-model="query" />
      <button @click="search()">SEARCH</button>
      <h1>{{ }}</h1>
    </form>
    <div class="results" v-if="results">
      <div v-for="result in results" v-bind:key="result">
        <img v-bind:src="result.links[0].href" />
      </div>
    </div>

    <b-iconstack font-scale="5" animation="spin">
      <b-icon stacked icon="search" variant="primary" scale="0.75" shift-v="-0.25"></b-icon>
      <b-icon icon="star-fill" animation="fade" font-scale="3" variant="dark"></b-icon>
    </b-iconstack>
  </div>
</template>
<script>
import axios from "axios";
export default {
  name: "search",
  data() {
    return {
      msg: "Search",
      query: "",
      results: "",
    };
  },
  methods: {
    getResult(query) {
      axios
        .get(
          "https://images-api.nasa.gov/search?q=" + query + "&media_type=image"
        )
        .then((response) => {
          console.log(response.data.collection.items);
          this.results = response.data.collection.items.slice(1, 20);
        });
    },
  },
};
</script>

