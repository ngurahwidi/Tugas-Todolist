<template>
  <div class="overflow-x-auto">
    <table class="table mt-6">
      <!-- head -->
      <thead>
        <tr>
          <th>Name</th>
          <th>Action</th>
        </tr>
      </thead>
      <tbody>
        <!-- row 1 -->
        <tr v-for="task in tasks" :key="task.id">
          <td>
            <span
              :class="{ completed: task.completed }"
              @click="$emit('toggle-task', task.id)"
            >
              {{ task.title }}
            </span>
          </td>
          <td>
            <button
              @click="$emit('delete-task', task.id)"
              class="btn btn-error btn-sm"
            >
              Delete
            </button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
  <!-- <ul class="flex flex-col justify-center items-center mt-6 w-full">
    <li
      v-for="task in tasks"
      :key="task.id"
      class="flex gap-10 justify-center items-center mt-3"
    >
      <span
        :class="{ completed: task.completed }"
        @click="$emit('toggle-task', task.id)"
      >
        {{ task.title }}
      </span>
      <button
        @click="$emit('delete-task', task.id)"
        class="btn btn-error btn-sm"
      >
        Delete
      </button>
    </li>
  </ul> -->
</template>

<script>
export default {
  props: ["tasks"],
};
</script>

<style>
.completed {
  text-decoration: line-through;
}
</style>
