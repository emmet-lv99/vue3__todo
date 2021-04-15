<template>
  <div id="app">
    <div class="top">
      <TodoHeader />
      <div>
        <TodoTitle />
        <TodoInput />
      </div>
    </div>
    <div class="body">
      <div>
        <TodoController />
        <TodoList />
      </div>
      <TodoFooter />
    </div>
  </div>
</template>

<script>
import { reactive } from "vue"
import TodoController from "@/components/TodoController.vue"
import TodoFooter from "@/components/TodoFooter.vue"
import TodoHeader from "@/components/TodoHeader.vue"
import TodoInput from "@/components/TodoInput.vue"
import TodoList from "@/components/TodoList.vue"
import TodoTitle from "@/components/TodoTitle.vue"

export default {
  name: "App",
  components: {
    TodoController,
    TodoFooter,
    TodoHeader,
    TodoInput,
    TodoList,
    TodoTitle,
  },
  setup() {
    const state = reactive({
      count: 0,
    })

    return {
      state,
    }
  },
}
</script>

<style lang="scss">
@import "./assets/style/_reset";
.top {
  width: 100%;
  min-height: 43.6rem;
  padding: 0 $padding 4.5rem;
  background-image: linear-gradient(145deg, #3770cc 20%, #ce91c9 84%);
}
.body {
  padding: 3rem $padding;
  background-color: #efefef;
}
</style>
