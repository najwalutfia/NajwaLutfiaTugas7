<!-- src/App.vue -->
<template>
  <div id="app">
    <TodoList />
  </div>
</template>

<script>
import TodoList from './components/TodoList.vue'

export default {
  components: {
    TodoList
  }
}
</script>


<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Poppins', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color: #f0f0f0;
  margin: 0;
  padding: 0;
}

#app {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background: linear-gradient(135deg, #f6d365 0%, #85f9fd 80%);
}

.todo-app {
  max-width: 500px;
  width: 100%;
  margin: 0 auto;
  padding: 20px;
  background-color: #fff;
  border-radius: 15px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
}

h1 {
  font-size: 28px;
  margin-bottom: 20px;
  text-align: center;
  color: #333;
}

.input-container {
  display: flex;
  justify-content: space-between;
}

input[type="text"] {
  width: calc(100% - 100px);
  padding: 12px;
  border: 2px solid #ddd;
  border-radius: 10px;
  margin-right: 10px;
  font-size: 16px;
  transition: border-color 0.3s;
}

input[type="text"]:focus {
  outline: none;
  border-color: #ff9a9e;
}

button {
  padding: 12px 20px;
  background-color: #ff9a9e;
  color: #fff;
  border: none;
  border-radius: 10px;
  cursor: pointer;
  font-size: 16px;
  transition: background-color 0.3s;
}

button:hover {
  background-color: #f4787e;
}

ul {
  padding: 0;
  margin-top: 20px;
  list-style: none;
}

li {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 10px 0;
  border-bottom: 1px solid #eee;
  font-size: 18px;
}

li:last-child {
  border-bottom: none;
}

.todo-item {
  display: flex;
  align-items: center;
}

.completed span {
  text-decoration: line-through;
  color: #888;
}

li span {
  margin-right: auto;
  cursor: pointer;
  transition: color 0.3s;
}

li span:hover {
  color: #ff9a9e;
}

input[type="checkbox"] {
  margin-right: 15px;
  width: 18px;
  height: 18px;
  cursor: pointer;
}

.remove-btn {
  background-color: #ff4d4d;
  border: none;
  border-radius: 5px;
  color: white;
  padding: 5px 10px;
  cursor: pointer;
  font-size: 14px;
  transition: background-color 0.3s;
}

.remove-btn:hover {
  background-color: #e60000;
}

p {
  text-align: center;
  margin-top: 20px;
  color: #333;
  font-size: 16px;
}
</style>
