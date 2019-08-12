<template>
  <div class="specific-joke">
    <nuxt-link :to="'jokes/' + joke.id">{{ truncatedJoke }}</nuxt-link>
  </div>
</template>

<script>
import _ from "lodash";

export default {
  name: "SpecificJoke",
  props: {
    joke: {
      type: Object,
      required: true
    },
    truncate: {
      type: Boolean,
      required: false,
      default: () => true
    }
  },
  computed: {
    truncatedJoke() {
      return this.truncate
        ? _.truncate(this.joke.joke, {
            length: 50,
            separator: " "
          })
        : this.joke.joke;
    }
  }
};
</script>

<style scoped>
.specific-joke {
  padding: 20px;
  margin: 5px;
  background-color: #eeeeee;
}
</style>
