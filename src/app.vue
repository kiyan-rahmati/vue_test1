<script setup>
import { provide, reactive } from 'vue';
import TaskForm from './TaskForm.vue';
import TaskList from './TaskList.vue';
const tasks = reactive([])

function addTask(task){
  tasks.push({text: task , completed: false})
}
function removeTask(index){
  tasks.splice(index, 1)
}
function toggleTask(index){
  tasks[index].completed = !tasks[index].completed
}
provide("removeTask" ,removeTask )
provide("toggleTask" , toggleTask)
</script>
<template>
    <div class="app-container">
    <h1>Todo project</h1>
    <TaskForm @add-task="addTask"/>
    <TaskList :tasks="tasks"/>
    </div>
</template>


<style>
.app-container {
  max-width: 400px;
  margin: 40px auto;
  background: #252525d3;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 10px rgba(255, 255, 255, 0.236);
  text-align: center;
}
h1 {
  font-size: 24px;
  color: #ffffff;
}
</style>
