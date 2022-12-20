<template>
  <form @submit.prevent="addItemAndClear(todo)">
    <div class="row align-content-center mt-3">
      <div class="col-sm-2"></div>
      <div class="form-group col-sm-8">
        <label for="newToDo" class="text-white">New ToDo</label>
        <input
          v-model="todo"
          type="text"
          class="form-control mt-2"
          id="newToDo"
        />
      </div>
      <div class="col-sm-2"></div>
    </div>
    <div class="row align-content-center mt-3">
      <div class="col-sm-2"></div>
      <div class="col-sm-8">
        <button type="submit" class="btn btn-primary btn-block col-sm-12">
          Add ToDo
        </button>
      </div>
      <div class="col-sm-2"></div>
    </div>
  </form>
</template>

<script setup>
import { ref } from 'vue';
import { useTodoListStore } from '../stores/todoList';

const todo = ref('');

const store = useTodoListStore();

function addItemAndClear(item) {
  if (item.length === 0) {
    return;
  }

  store.addTodo(item);
  todo.value = '';
}
</script>
