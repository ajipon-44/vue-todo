<script setup>
import { ref, watch } from 'vue';
const todo = ref('');
const todos = ref([]);
const createTodo = () => {
  todos.value.push(todo.value);
  todo.value = '';
};
</script>
<template>
  <div>
    <input v-model="todo" type="text" />
    <button @click="createTodo">create todo</button>
    <ul>
      <!-- todos 配列の内容を表示 -->
      <li v-for="(item, index) in todos" :key="index">{{ item }}</li>
    </ul>
  </div>
</template>
