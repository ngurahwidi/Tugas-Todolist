<template>
  <div class="flex gap-2 justify-center items-center">
    <input
      v-model="title"
      placeholder="Add a new task"
      class="rounded-lg p-2"
    />
    <button @click="submitTask" class="btn btn-primary btn-sm">Add Task</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "",
    };
  },
  methods: {
    submitTask() {
      if (this.title.trim()) {
        this.$emit("add-task", {
          id: Date.now(),
          title: this.title,
          completed: false,
        });
        this.title = "";
      }
    },
  },
};
</script>
