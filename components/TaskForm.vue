<template>
  <form @submit="addNewTask" class="flex gap-2 my-4">
    <input
      class="p-3 border border-slate-200 rounded-md flex-grow hover:bg-slate-50 focus:outline-none focus:ring-2 focus:ring-indigo-500"
      type="text"
      name="task"
      v-model="task"
    />
    <button
      @click="addNewTask"
      type="button"
      class="py-3 px-5 bg-indigo-600 rounded-md font-semibold text-white hover:bg-indigo-500"
    >
      Add Task
    </button>
  </form>
</template>

<script>
export default {
  name: "TaskForm",
  data() {
    return {
      task: "",
    };
  },
  methods: {
    addNewTask(e) {
      e.preventDefault();
      this.$emit("createTask", { id: Math.random(), name: this.task });
      this.task = "";
    },
  },
};
</script>
