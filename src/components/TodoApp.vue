<template>
  <div class="container">
    <div class="row align-content-center mt-3">
      <div class="col-sm-4"></div>
      <div class="col-sm-4">
        <h1 class="text-white text-center">ToDo App</h1>
      </div>
      <div class="col-sm-4"></div>
    </div>

    <TodoForm />
    <div class="row align-content-center mt-5">
      <div class="col-sm-4"></div>
      <div class="col-sm-4">
        <h2 class="text-white text-center border-bottom border-primary">
          ToDo List
        </h2>
      </div>
      <div class="col-sm-4"></div>
    </div>
    <TodoList />
  </div>
</template>

<script setup>
import TodoForm from '../components/TodoForm.vue';
import TodoList from './TodoList.vue';
</script>
