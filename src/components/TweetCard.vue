<template>
  <div v-if="view_status === 'Card View'" class="tweet_card">
    <p>{{ tweet_content }}</p>
    <h4>{{ tweet_user }}</h4>
    <h5>{{ tweet_date }}</h5>
  </div>
  <div v-else class="tweet_list">
    <p>{{ tweet_content }}</p>
    <h4>{{ tweet_user }}</h4>
    <h5>{{ tweet_date }}</h5>
  </div>
</template>

<script>
export default {
  name: "tweet-card",
  props: {
    tweet_content: String,
    tweet_user: String,
    tweet_date: String,
    view_status: String,
  },
};
</script>

<style scoped>
</style>