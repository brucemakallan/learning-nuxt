<template>
  <div class="about-page">
    <h1>This is a learning application that delivers corny Dad Jokes</h1>
    <p>This project is written in Vue JS and used to learn Nuxt</p>
    <ol>
      <li v-for="(joke, index) in jokes" :key="index">{{ joke.joke }}</li>
    </ol>
  </div>
</template>

<script>
import axios from "axios";

const API = "https://icanhazdadjoke.com/search";

export default {
  name: "Jokes",
  head() {
    return {
      title: "Jokes",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Get all the best dad jokes your heart can take"
        }
      ]
    };
  },
  data() {
    return {
      jokes: []
    };
  },
  async created() {
    const config = {
      headers: {
        Accept: "application/json"
      }
    };
    await axios
      .get(API, config)
      .then(res => (this.jokes = res.data.results))
      .catch(error => console.log(error.data));
  }
};
</script>

<style>
</style>
