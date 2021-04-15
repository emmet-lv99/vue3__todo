<template>
  <div class="add">
    <div class="main-input">
      <input type="text" class="add__input" placeholder="Enter your task" />
      <button class="add__button"></button>
    </div>
  </div>
</template>

<script>
import { reactive, toRefs } from "vue"

export default {
  name: "input",
  setup() {
    const state = reactive({
      count: 0,
    })

    return {
      ...toRefs(state),
    }
  },
}
</script>

<style lang="scss" scoped>
.add {
  position: relative;
  max-width: $max-width;
  margin: 0 auto;
  .main-input {
    @include animation(fadeShow, 800ms, 1, 900ms);
  }
}
</style>
