<template>
  <div v-for="task in tasks" :key="task.key">
    <Task
      @toggle-reminder="$emit('toggle-reminder', task.id)"
      @delete-task="$emit('delete-task', task.id)"
      :task="task"
    />
  </div>
</template>

<script>
import Task from "./Task.vue";

export default {
  name: "Tasks",
  components: {
    Task,
  },
  props: {
    tasks: {
      type: Array,
    },
  },
  emits: ["delete-task", "toggle-reminder"],
};
</script>
