<template>
  <div class="header">
    <h1 class="logo">
      <span class="blind">
        My Todo
      </span>
    </h1>
    <p class="header__date">{{ state.timeStamp }}</p>
  </div>
</template>

<script>
import { reactive } from "vue"

export default {
  name: "Header",
  setup() {
    const state = reactive({
      timeStamp: "",
    })

    const now = new Date()
    const month = now.getMonth() + 1
    const date = now.getDate()
    const weekList = ["Sun.", "Mon.", "Tue.", "Wed.", "Thu.", "Fri.", "Sat."]
    const week = weekList[now.getDay()]
    state.timeStamp = `${month}/${date} ${week}`

    return {
      state,
      now,
      month,
      date,
      weekList,
      week,
    }
  },
}
</script>

<style lang="scss" scoped>
.header {
  max-width: $max-width;
  margin: 0 auto;
  padding: 20px 0 55px;
  color: #fff;
  @include flexbox;
  @include align-items(center);
  @include justify-content(space-between);
  &__date {
    letter-spacing: 0.02rem;
    font-size: 1.2rem;
  }
}
.logo {
  width: 5.8rem;
  height: 1.6rem;
  background-size: 100%;
  background-position: 50% 50%;
  background-repeat: no-repeat;
  background-image: icon("logo", "ffffff");
}
</style>
