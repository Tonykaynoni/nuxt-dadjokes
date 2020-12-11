<template>
  <div>
    <nuxt-link to="/jokes" class="back-button">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        width="24"
        height="24"
        viewBox="0 0 24 24"
        fill="none"
        stroke="currentColor"
        stroke-width="2"
        stroke-linecap="round"
        stroke-linejoin="round"
        class="feather feather-chevrons-left"
      >
        <polyline points="11 17 6 12 11 7"></polyline>
        <polyline points="18 17 13 12 18 7"></polyline>
      </svg>
      Back To Jokes
    </nuxt-link>
    <h2 class="joke-style">{{ joke }}</h2>
    <small>Joke ID: {{ $route.params.id }}</small>
  </div>
</template>
<script>
import axios from "axios";
export default {
  data() {
    return { joke: "" };
  },
  async created() {
    const config = {
      headers: {
        Accept: "application/json"
      }
    };

    try {
      const res = await axios.get(
        `https://icanhazdadjoke.com/j/${this.$route.params.id}`,
        config
      );
      this.joke = res.data.joke;
      console.log(res.data);
    } catch (error) {
      console.log(error);
    }
  }
};
</script>

<style scoped>
.joke-style::after {
  margin-top: 0.7rem;
  content: "";
  border: 2px solid #526480;
  border-radius: 0.5rem;
  width: 50%;
  display: block;
}

.joke-style {
  margin-top: 1rem;
  font-weight: 900;
  font-family: Quicksand, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    "Helvetica Neue", Arial, "Noto Sans", sans-serif, "Apple Color Emoji",
    "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji" !important;
}
.back-button {
  display: flex;
}
.back-button:hover {
  color: #446292;
  font-weight: 600;
  transition: transform 450ms;
  transform: scale(1.02);
}
</style>
