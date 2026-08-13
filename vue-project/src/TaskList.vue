<script setup lang="ts">
import TaskItem from './TaskItem.vue';

</script>

<template >
    <ul class="task-list">
        <TaskItem/>
    </ul>
</template>

<style>
.task-list {
    list-style: none;
    padding: 0;
}
</style>