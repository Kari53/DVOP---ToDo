<template>
  <div id="app">
    <TodoList />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import TodoList from '@/components/TodoList.vue'; 

export default defineComponent({
  name: 'App',
  components: {
    TodoList,
  },
});
</script>

<style scoped>
#app {
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: Arial, sans-serif;
  text-align: center;
}
</style>
