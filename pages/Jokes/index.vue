<template>
  <div>
    <SearchJoke v-on:search-text="searchText"/>
    <h1>Jokes Page</h1>
    <Joke v-bind:key="joke.id" v-for="joke in jokes" v-bind:id="joke.id" v-bind:joke="joke.joke"/>
  </div>
</template>

<script>
// Importing Axios
import axios from "axios";
// Importing components
import Joke from "../../components/Joke";
import SearchJoke from "../../components//SearchJoke";

export default {
  components: {
    Joke,
    SearchJoke
  },
  // Data
  data() {
    return {
      jokes: []
    };
  },
  // Head Tag
  head() {
    return {
      title: "Dad Jokes",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Read best dad jokes"
        }
      ]
    };
  },
  // Lifecycle Methods
  async created() {
    // HTTP Config Object - Headers
    const config = {
      headers: {
        Accept: "application/json"
      }
    };
    try {
      // Fetch Data
      const res = await axios.get("https://icanhazdadjoke.com/search", config);
      this.jokes = res.data.results;
    } catch (err) {
      throw new Error(err);
    }
  },
  // Methods
  methods: {
    // Search For Jokes Method
    async searchText(text) {
      // HTTP Config Object - Headers
      const config = {
        headers: {
          Accept: "application/json"
        }
      };
      try {
        // Fetch Data
        const res = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`, config);
        this.jokes = res.data.results;
      } catch (err) {
        throw new Error(err);
      }
    }
  }
};
</script>

<style scoped>
</style>
