<template>
  <div id="app">
    <section id="tweet_location">
      <button id="toggle_view_button" @click="toggle_view">Card View</button>
      <tweet-card
      v-for="tweet in tweets" :key="tweet.tweet_content" 
      :view_status="toggle_view"
      :tweet_content="tweet.tweet_content"
      :tweet_user="tweet.tweet_user"
      :tweet_date="tweet.tweet_date"> </tweet-card>
    </section>
  </div>
</template>

<script>
import TweetCard from "./components/TweetCard.vue";
export default {
  name: "App",
  components: {
    TweetCard,
  },
  methods: {
    toggle_view() {
      var toggle_view_button = document.getElementById('toggle_view_button');
      if(toggle_view_button.innerText === "Card View") {
        toggle_view_button.innerText = "List View";
        return "List View"
      } else if(toggle_view_button.innerText === "List View") {
        toggle_view_button.innerText = "Card View";
        return "Card View"
      }
    }
  },
  data() {
    return {
      tweets: [
        {
          tweet_content: "This is a sample tweet #realism",
          tweet_user: "randomUser123",
          tweet_date: "03/12/16",
        },
        {
          tweet_content: "This is aother sample tweet #realism",
          tweet_user: "weirdUser123",
          tweet_date: "04/11/17",
        },
        {
          tweet_content: "This is just another sample tweet #realism",
          tweet_user: "madeUp_user",
          tweet_date: "23/12/19",
        },
        {
          tweet_content: "This is a real tweet #realism",
          tweet_user: "sameUser123",
          tweet_date: "13/02/20",
        },
        {
          tweet_content: "Don't make me tweet this #realism",
          tweet_user: "dareUser35324523",
          tweet_date: "03/12/20",
        },
        {
          tweet_content: "I like to eat apples #realism",
          tweet_user: "appleEater101",
          tweet_date: "05/12/20",
        },
        {
          tweet_content: "I just ate a hotdog #sointeresting #realism",
          tweet_user: "glutton45",
          tweet_date: "13/11/20",
        },
        {
          tweet_content: "I can't think of anymore #realism",
          tweet_user: "uselessUser",
          tweet_date: "01/12/20",
        },
        {
          tweet_content: "I was made fun of as a kid #confession #realism",
          tweet_user: "bulliedUserop",
          tweet_date: "02/12/21",
        },
        {
          tweet_content: "made up tweet #realism",
          tweet_user: "finallyDone",
          tweet_date: "02/12/21",
        },
      ],
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
