<template>
  <div id="app">
    <!-- section containing tweets class is defined here for card view as default -->
    <section class="section_card_view" id="tweet_location">
      <!-- button to toggle between card view and list view -->
      <button id="toggle_view_button" @click="toggle_view">Card View</button>
  <!-- for loop to generate tweets from the data below -->
      <tweet-card
        class="tweet_card"
        v-for="tweet in tweeter"
        :key="tweet.tweet_content"
        :tweet_content="tweet.tweet_content"
        :tweet_user="tweet.tweet_user"
        :tweet_date="tweet.tweet_date"
      >
      </tweet-card>
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
  data() {
    return {
      // variable to store view status
      cardView: "card_view",
      // tweet data entered manually
      tweeter: [
        {
          tweet_content: "This is a sample tweet #realism",
          tweet_user: "randomUser123",
          tweet_date: "03/12/16",
        },
        {
          tweet_content: "This is another sample tweet #realism",
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
  methods: {
    // function to change view
    toggle_view() {
      var toggle_view_button = document.getElementById("toggle_view_button");
      // conditional to determine if the current status card view or list view
      if (toggle_view_button.innerText === "Card View") {
        // change innertext of button
        toggle_view_button.innerText = "List View";
        // define and toggle class of section container containing tweets
        var tweet_section = document.getElementById('tweet_location');
        tweet_section.classList.toggle("section_card_view");
        tweet_section.classList.toggle("section_list_view");
        // define and toggle class of individual tweet card
        var tweet_cards = document.getElementsByClassName("tweet_card");
        for (var i = 0; i < tweet_cards.length; i = i-i) {
          tweet_cards[i].classList.toggle("tweet_list");
          tweet_cards[i].classList.toggle("tweet_card");
        }
        // conditional to change from list view back to card view
      } else if (toggle_view_button.innerText === "List View") {
        // change innertext of button
        toggle_view_button.innerText = "Card View";        
        // define and toggle class of section container containing tweets
        tweet_section = document.getElementById('tweet_location');
        tweet_section.classList.toggle("section_card_view");
        tweet_section.classList.toggle("section_list_view");
        // define and toggle class of individual tweet card
        tweet_cards = document.getElementsByClassName("tweet_list");
        for (i = 0; i < tweet_cards.length; i = i-i) {
          tweet_cards[i].classList.toggle("tweet_card");
          tweet_cards[i].classList.toggle("tweet_list");
        }
      }
    },
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

#tweet_location {
  padding: 50px;
  background-color: rgba(135, 207, 235, 0.705);
  border-radius: 25px;
}

.tweet_card {
  background-color: rgba(255, 250, 250, 0.493);
  border-radius: 25px;
  padding: 15px;
}

.section_card_view {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  column-gap: 10px;
  row-gap: 10px;
}

.tweet_list {
  background-color: rgba(255, 250, 250, 0.493);
  border-radius: 25px;
padding-left: 20px;
}

.section_list_view {
text-align: left;
}

#toggle_view_button {
  position: absolute;
  left: calc(50% - 40px);
  top: 10px;
}
</style>
