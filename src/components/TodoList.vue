<template>
    <div>
      <h2>Your Tasks</h2>
      <input v-model="newTask" placeholder="Enter a task" />
      <button @click="addTask">Add Task</button>

      <ul>
        <li v-for="(task, index) in tasks" :key="index">
          {{ task }} 
          <button @click="removeTask(index)">Remove</button>
        </li>
      </ul>
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent, ref } from 'vue'; 
  
  export default defineComponent({
    name: 'TodoList',
  
    setup() {
      const tasks = ref<string[]>([]); 
      const newTask = ref(''); 
  
      const addTask = () => {
        if (newTask.value.trim() !== '') {
          tasks.value.push(newTask.value);
          newTask.value = '';
        }
      };
  
      const removeTask = (index: number) => {
        tasks.value.splice(index, 1);
      };
  
      return {
        tasks,
        newTask,
        addTask,
        removeTask,
      };
    },
  });
  </script>
  
  <style scoped>
  input {
    padding: 8px;
    font-size: 14px;
  }
  
  button {
    margin-left: 10px;
    padding: 8px 12px;
    font-size: 14px;
    background-color: rgb(255, 0, 0);
    color: white;
    border: none;
    cursor: pointer;
  }
  
  ul {
    list-style-type: none;
    padding: 0;
  }
  
  li {
    margin: 10px 0;
    display: flex;
    justify-content: space-between;
  }
  
  </style>
  