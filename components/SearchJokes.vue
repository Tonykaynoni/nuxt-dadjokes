<template>
  <form @submit.prevent="onSubmit">
    <input type="text" v-model="text" placeholder="Search Jokes..." />
    <button type="submit">Search Jokes</button>
  </form>
</template>

<script>
export default {
  name: "SearchJokes",
  data() {
    return {
      text: ""
    };
  },
  methods: {
    onSubmit() {
      this.$emit("search-text", this.text);
      this.text = "";
    }
  }
};
</script>

<style>
input {
  border: 1px solid #ebeced;
  padding: 0.5rem;
  border-radius: 0.25rem;
  margin-right: 0.2rem;
}
form {
  display: flex;
}

button {
  background-color: #00c58e;
  padding: 0.5rem;
  border-radius: 0.25rem;
  color: #fff;
  cursor: pointer;
  text-transform: uppercase;
  border: 0 solid #e2e8f0;
  font-family: Quicksand, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    "Helvetica Neue", Arial, "Noto Sans", sans-serif, "Apple Color Emoji",
    "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
  line-height: 1.5;
  font-weight: 500;
}
</style>
