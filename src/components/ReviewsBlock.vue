<template>
  <div class="reviews">
    <div class="reviews__nav">
      <ul class="reviews__nav-links">
        <li>
          <a class="reviews__nav-link active" href="#">Latest reviews</a>
        </li>
        <li>
          <a class="reviews__nav-link" href="#">All reviews</a>
        </li>
      </ul>

      <div class="reviews__nav-counters">
        <button class="reviews__like-btn">131</button>
        <button class="reviews__comments-btn">14</button>
      </div>
    </div>

    <ul class="reviews__list">
      <li v-for="review in reviews" :key="review.id" class="reviews__list-item">
        <div class="reviews__info">
          <div class="reviews__author">{{ review.author }}</div>
          <div class="reviews__date">{{ review.date }}</div>
        </div>

        <div class="reviews__body">{{ review.body }}</div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "ReviewsBlock",
  props: {
    reviews: {
      type: Array,
      required: true,
      default: () => [],
    },
  },
};
</script>

<style lang="scss" scoped>
.reviews {
  margin-bottom: 22px;

  &__nav {
    margin-bottom: 13px;
  }

  &__nav,
  &__nav-links,
  &__nav-counters {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  &__nav-links li:not(:last-child) {
    margin-right: 8px;
  }

  &__nav-link {
    color: #005da1;
    text-decoration: underline;
    &.active {
      font-size: 16px;
      font-weight: 700;
      color: #333333;
      text-decoration: none;
    }
  }

  &__nav-counters {
    font-size: 12px;
  }

  &__like-btn,
  &__comments-btn {
    position: relative;
    padding-left: 16px;
  }

  &__like-btn::before,
  &__comments-btn::before {
    content: "";
    position: absolute;
    left: 0;
    top: 50%;
    background-size: cover;
    transform: translateY(-50%);
  }

  &__like-btn {
    margin-right: 16px;
  }

  &__like-btn::before {
    width: 12px;
    height: 11px;
    background-image: url("@/assets/like.svg");
  }

  &__comments-btn::before {
    width: 13px;
    height: 13px;
    background-image: url("@/assets/comment.svg");
  }

  &__list-item:not(:last-child) {
    margin-bottom: 17px;
  }

  &__info {
    display: flex;
    align-items: center;
    margin-bottom: 13px;
  }

  &__author {
    margin-right: 8px;
    font-weight: 700;
  }

  &__date {
    font-size: 11px;
    color: #808080;
  }

  &__body {
    position: relative;
    padding: 12px 20px;
    border: 1px solid #c4cbcf;
    background-color: #f2fbff;
    box-shadow: 0px 4px 10px rgba(128, 128, 128, 0.1);
  }

  &__body::before,
  &__body::after {
    content: "";
    position: absolute;
    top: -13px;
    left: 22px;
    border: 6px solid transparent;
    border-bottom: 6px solid #c4cbcf;
    border-left: 6px solid #c4cbcf;
  }

  &__body::after {
    top: -11px;
    left: 23px;
    border: 6px solid transparent;
    border-bottom: 6px solid #f2fbff;
    border-left: 6px solid #f2fbff;
  }
}
</style>
