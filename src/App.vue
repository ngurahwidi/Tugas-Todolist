<script>
import AddTask from "./components/AddTask.vue";
import TaskList from "./components/TaskList.vue";

export default {
  components: {
    AddTask,
    TaskList,
  },
  data() {
    return {
      tasks: [],
    };
  },
  methods: {
    addTask(task) {
      this.tasks.push(task);
    },
    deleteTask(taskId) {
      this.tasks = this.tasks.filter((task) => task.id !== taskId);
    },
    toggleTask(taskId) {
      const task = this.tasks.find((task) => task.id === taskId);
      task.completed = !task.completed;
    },
  },
};
</script>

<template>
  <div id="app">
    <h1 class="text-3xl font-bold mb-4 text-center">To-Do List</h1>
    <AddTask @add-task="addTask" />
    <TaskList
      :tasks="tasks"
      @delete-task="deleteTask"
      @toggle-task="toggleTask"
    />
  </div>
</template>

<style scoped></style>
