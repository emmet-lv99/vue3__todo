<template>
  <div class="add">
    <div class="main-input">
      <input
        type="text"
        class="add__input"
        placeholder="Enter your task here"
        v-model="state.newTodoItem"
        @keyup.enter="addTodoItem"
      />
      <button class="add__button"></button>
    </div>
  </div>
</template>

<script>
import { reactive } from "vue"

export default {
  name: "input",
  setup() {
    const state = reactive({
      newTodoItem: "",
    })

    const addTodoItem = () => {
      if (state.newTodoItem !== "") {
        const value = {
          item: state.newTodoItem,
          date: `${new Date().getMonth() + 1}/${new Date().getDate()}`,
          completed: false,
        }
        localStorage.setItem(state.newTodoItem, JSON.stringify(value))
        clearInput()
      }
    }

    const clearInput = () => (state.newTodoItem = "")
    return {
      state,
      addTodoItem,
      clearInput,
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
