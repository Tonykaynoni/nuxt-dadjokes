<template>
  <div>
    <p>
      Largest selection of dad jokes on the internet using
      <a href="https://icanhazdadjoke.com/">icanhazdadjoke.com</a>
    </p>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: "About Us",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Best place for corny dad jokes"
        }
      ]
    };
  }
};
</script>
