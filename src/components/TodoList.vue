<template>
  <div class="todo-app">
    <h1>Todo List Najwa Lutfia</h1>
    <input v-model="newTask" @keyup.enter="addNewTodo" placeholder="Add a new task" />
    <button @click="addNewTodo">Add</button>

    <ul>
      <li v-for="(todo, index) in todoStore.todos" :key="index">
        <input type="checkbox" v-model="todo.completed">
        <span :class="{ completed: todo.completed }">{{ todo.text }}</span>
        <button @click="removeTask(index)">Remove</button>
      </li>
    </ul>

    <p>Tasks left: {{ todoStore.incompleteCount }}</p>
  </div>
</template>

<script>
import { useTodoStore } from '../stores/todoStore'
import { ref } from 'vue'

export default {
  setup() {
    const todoStore = useTodoStore()
    const newTask = ref('')

    function addNewTodo() {
      if (newTask.value.trim() !== '') {
        todoStore.addTodo(newTask.value)
        newTask.value = ''
      }
    }

    function removeTask(index) {
      todoStore.removeTodo(index)
    }

    return {
      todoStore,
      newTask,
      addNewTodo,
      removeTask
    }
  }
}
</script>

<style scoped>
.todo-app {
  max-width: 400px;
  margin: auto;
  padding: 1rem;
  border: 1px solid #ccc;
  border-radius: 5px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  background-color: #fff;
}

input[type="checkbox"] {
  margin-right: 5px;
}

input {
  width: calc(100% - 50px);
  padding: 0.5rem;
  margin-right: 5px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

button {
  padding: 0.5rem;
  border: none;
  background-color: #df82df;
  color: white;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background-color: #82dfcb;
}

ul {
  list-style-type: none;
  padding: 0;
  margin: 1rem 0;
}

li {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.5rem 0;
  border-bottom: 1px solid #ccc;
}

.completed {
  text-decoration: line-through;
  color: #888;
}

li span {
  cursor: pointer;
}
</style>
