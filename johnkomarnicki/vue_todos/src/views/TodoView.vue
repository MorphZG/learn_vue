<script setup>
  import TodoCreator from "../components/TodoCreator.vue";
  import { ref } from "vue";
  import { uid } from "uid"

  const todoList = ref([]);
  function createTodo(event) {
    todoList.value.push({
      id: uid(),
      event,
      isCompleted: null,
      isEditing: null,
    })
  }
</script>

<template>
  <main>
    <h1>Create Todo</h1>
    <TodoCreator @create-todo="createTodo" />
  </main>
</template>

<style lang="scss" scoped>
  main {
    display: flex;
    flex-direction: column;
    max-width: 500px;
    width: 100%;
    margin: 0 auto;
    padding: 40px 16px;

    h1 {
      margin-bottom: 16px;
      text-align: center;
    }
  }
</style>
