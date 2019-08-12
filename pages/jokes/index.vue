<template>
  <div class="about-page">
    <h1>This is a learning application that delivers corny Dad Jokes</h1>
    <p>This project is written in Vue JS and used to learn Nuxt</p>
  </div>
</template>

<script>
export default {
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
  }
};
</script>

<style>
</style>
