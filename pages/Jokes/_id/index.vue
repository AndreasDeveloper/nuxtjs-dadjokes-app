<template>
  <div>
      <h2>{{ joke }}</h2>
      <nuxt-link to="/jokes">Back To Jokes</nuxt-link>
      <hr />
      <small>Joke ID: {{ $route.params.id }}</small>
  </div>
</template>

<script>
// Importing Axios
import axios from 'axios';

export default {
    data() {
        return {
            joke: {}
        }
    },
    // Lifecycle Hooks
    async created() {
        // HTTP Config Object - Headers
        const config = {
            headers: {
                'Accept': 'application/json'
            }
        };
        try {
            // Fetch Data
            const res = await axios.get(`https://icanhazdadjoke.com/j/${this.$route.params.id}`, config);
            this.joke = res.data.joke;
        } catch (err) {
            throw new Error(err);
        }
    }
};
</script>

<style scoped>
</style>
