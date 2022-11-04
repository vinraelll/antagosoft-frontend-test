<template>
  <form class="review-form" @submit.prevent>
    <textarea
      v-model="body"
      class="review-form__textarea"
      @keydown.enter.ctrl="onSubmit"
    ></textarea>
    <button class="review-form__btn" type="submit" @click="onSubmit">
      Send a message
    </button>
  </form>
</template>

<script>
export default {
  name: "ReviewForm",
  props: {
    reviews: {
      type: Array,
      required: true,
    },
  },
  emits: ["on-new-review"],
  data() {
    return {
      body: "",
    };
  },
  methods: {
    onSubmit() {
      if (!this.body) return;

      this.$emit("on-new-review", {
        author: "Anonymous",
        body: this.body,
        date: this.getDate(),
        id: Date.now(new Date()),
      });
      this.body = "";
    },
    getDate() {
      const options = {
        day: "numeric",
        year: "numeric",
        month: "short",
      };
      return new Date().toLocaleString("en-GB", options);
    },
  },
};
</script>

<style lang="scss" scoped>
.review-form {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 28px 21px 34px 21px;
  background-color: #f2f2f2;

  &__textarea {
    max-width: 100%;
    width: 100%;
    min-height: 63px;
    margin-bottom: 23px;
    padding: 4px;
    border: 1px solid #000000;
    border-radius: 1px;
    resize: none;
  }

  &__btn {
    padding: 12px 48px;
    font-family: "PT Sans", sans-serif;
    font-weight: 700;
    font-size: 16px;
    background-color: #fdd639;
    border-radius: 23px;
  }
}
</style>
