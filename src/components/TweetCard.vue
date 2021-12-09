<template>
  <div>
    <!-- to display content passed down by the parent -->
    <p>{{ tweet_content }}</p>
    <h4>{{ tweet_user }}</h4>
    <h5>{{ tweet_date }}</h5>
  </div>
</template>

<script>
export default {
  name: "tweet-card",
  // declare prop to be expected 
  props: {
    tweet_content: String,
    tweet_user: String,
    tweet_date: String,
  },
};
</script>

<style scoped>
</style>