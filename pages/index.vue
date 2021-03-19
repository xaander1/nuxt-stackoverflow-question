<template>
  <section>
    <h1>Testing custom error</h1>
    <p v-if="$fetchState.pending">Fetching mountains...</p>
    <PageError v-else-if="$fetchState.error" />
    <p v-else>Fetch success</p>
  </section>
</template>

<script>
import PageError from '~/components/PageError.vue'
export default {
  components : {
    PageError
  },
  async fetch() {
    await this.$axios.$get("https://api.nuxtjs.dev/mountain");
  },
  fetchOnServer: false,
};
</script>

<style scoped>
.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  display: block;
  font-weight: 400;
  font-size: 100px;
  color: #2E495E;
  letter-spacing: 1px;
  font-size: 6em;
}
.green {
  color: #00C48D;
}

.subtitle {
  font-weight: 300;
  font-size: 3em;
  color: #2E495E;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
