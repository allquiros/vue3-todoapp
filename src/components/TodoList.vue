<template>
  <div
    v-for="todo in todoList"
    :key="todo.id"
    class="row align-content-center mt-3"
  >
    <div class="col-sm-2"></div>
    <div
      class="col-sm-8 border border-light rounded-bottom p-2 border-opacity-50 text-white"
    >
      <span :class="{ completed: todo.completed }">{{ todo.item }}</span>
      <span
        class="badge text-bg-danger p-2 span-buttom"
        @click="deleteTodo(todo.id)"
        >Delete</span
      >
      <span
        class="badge text-bg-success p-2 span-buttom"
        @click.stop="toggleCompleted(todo.id)"
        >Complete</span
      >
    </div>
    <div class="col-sm-2"></div>
  </div>
</template>

<script setup>
import { useTodoListStore } from '../stores/todoList';
import { storeToRefs } from 'pinia';

const store = useTodoListStore();

// storeToRefs lets todoList keep reactivity:
const { todoList } = storeToRefs(store);

// destructuring action method doesn't require using storeToRefs:
const { toggleCompleted, deleteTodo } = store;
</script>

<style>
span {
  margin: 0 10px;
  cursor: pointer;
  font-size: large;
}

.span-buttom {
  float: right;
}
.completed {
  text-decoration: line-through 1px;
}
</style>
