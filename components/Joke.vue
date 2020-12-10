<template>
  <div class="joke">
    <nuxt-link :to="'/jokes/' + id">
      <p>{{ joke }}</p></nuxt-link
    >
  </div>
</template>

<script>
export default {
  name: "Joke",
  props: ["joke", "id"]
};
</script>

<style>
.joke {
  padding: 1rem;
  border: 1px dotted #ccc;
  margin: 1rem 0;
}
</style>
