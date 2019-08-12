<template>
  <div>
    <div class="one-joke">Joke ID: {{ $route.params.id }}</div>
    <Joke :joke="joke" :truncate="false"/>
  </div>
</template>

<script>
import axios from "axios";
import Joke from "../../../components/Joke";

const API = "https://icanhazdadjoke.com/j/";

export default {
  name: "JokePage",
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
      joke: {
        type: Object,
        required: true
      }
    };
  },
  async created() {
    const config = {
      headers: {
        Accept: "application/json"
      }
    };
    await axios
      .get(API + this.$route.params.id, config)
      .then(res => (this.joke = res.data))
      .catch(error => console.log(error.data));
  },
  components: {
    Joke
  }
};
</script>

<style>
</style>
