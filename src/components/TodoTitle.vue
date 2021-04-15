<template>
  <div class="title">
    <p class="title__text">
      <span class="title__messege">Good message,</span>
      <span class="title__name"></span>
    </p>
    <p class="title__task">
      <span class="title__task-top">
        You.ve got
      </span>
      <span class="title__task-count">
        <em class="title__task-left">1</em>
        <em class="title__task-total">2</em>
      </span>
      <span class="title__task-bottom">
        <span>tasks</span>
      </span>
      <span class="title__task-info"></span>
    </p>
  </div>
</template>

<script>
import { reactive } from "vue"

export default {
  name: "Title",
  setup() {
    const state = reactive({
      message: "Hello, nunuuNanNa~",
      taskTotal: 5,
    })

    return {
      state,
    }
  },
}
</script>

<style lang="scss" scoped>
.title {
  max-width: $max-width;
  margin: 0 auto;
  letter-spacing: 0.03rem;
  color: #fff;

  &__message {
    font-size: 1.6rem;
  }

  &__task {
    margin-top: 3.5rem;
    margin-bottom: 5rem;
    font-weight: bold;

    &-top {
      display: block;
      font-size: 2.6rem;
    }

    &-total {
      font-size: 5.4rem;
      line-height: 110%;
    }
  }
}
</style>
