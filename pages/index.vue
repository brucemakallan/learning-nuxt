<template>
  <div class="homepage"></div>
</template>

<script>
export default {
  head() {
    return {
      title: "Welcome",
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
.homepage {
  width: 90%;
  margin: 30px auto;
}
</style>
