<template>
  <Fragment>
    <TaskForm @createTask="addTask" />
    <p v-if="tasks.length > 0" class="text-slate-500 mt-4 mb-1">All tasks</p>
    <Task
      v-for="item in tasks"
      :taskName="item.name"
      v-bind:key="item.id"
      :id="item.id"
      @removeTask="removeTask"
    />
  </Fragment>
</template>

<script>
export default {
  name: "IndexPage",
  data() {
    return {
      tasks: [],
    };
  },
  methods: {
    addTask(task) {
      this.tasks.push(task);
    },
    removeTask(id) {
      this.tasks = this.tasks.filter((task) => task.id !== id && task);
    },
  },
};
</script>
