<script setup>
import { ref } from 'vue';
import {uid} from 'uid'
import TodoCreater from '../components/TodoCreater.vue';
import TodoItem from '../components/TodoItem.vue';

const todoList = ref([]);

const createTodo = (todo)=>{
  console.log(todo);
todoList.value.push({
  id: uid(),
  todo,
  isCompleted: false,
  isEditing:null
})
}

</script>

<template>
  <main>
   <h1>Create Todo</h1>
   <TodoCreater @create-todo="createTodo" />
   <ul class="todo-list">
    <TodoItem v-for="todo in todoList" :todo="todo"/>
   </ul>
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

  .todo-list {
    display: flex;
    flex-direction: column;
    list-style: none;
    margin-top: 24px;
    gap: 20px;
  }

  .todos-msg {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
    margin-top: 24px;
  }
}
</style>
