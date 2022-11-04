<template>
  <main class="main">
    <UserInfo />
    <ReviewsBlock :reviews="reviews" />
    <ReviewForm :reviews="reviews" @on-new-review="addReview" />
  </main>
</template>

<script>
import UserInfo from "./components/UserInfo.vue";
import ReviewsBlock from "./components/ReviewsBlock.vue";
import ReviewForm from "./components/ReviewForm.vue";

export default {
  name: "App",
  components: {
    UserInfo,
    ReviewsBlock,
    ReviewForm,
  },
  data() {
    return {
      reviews: [
        {
          author: "Samuel Jackson",
          body: "Hey Eva! You're cool. Nice pic!",
          date: "13 apr 2022",
          id: "0",
        },
        {
          author: "Angela Deimon",
          body: "Thanks for your services! We really liked the ocean view room. We hope to cooperate in the near future. We are sure you will do everything to make our next holiday fantastic.",
          date: "10 apr 2022",
          id: "1",
        },
        {
          author: "Ronald Harris",
          body: "Eva, hello! There is such a question: How can I contact you if I am abroad in roaming?",
          date: "8 apr 2022",
          id: "2",
        },
      ],
    };
  },
  methods: {
    addReview(review) {
      this.reviews.push(review);
    },
  },
};
</script>

<style lang="scss">
.main {
  max-width: 740px;
  margin: 0 auto;
  padding: 0 10px;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 14px;
  line-height: 1.25;
  font-weight: 400;
  color: #333333;
}
</style>
