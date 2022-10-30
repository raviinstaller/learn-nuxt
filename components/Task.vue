<template>
  <div
    class="my-1 rounded-md border border-slate-200 flex justify-between p-3 h-14 items-center hover:bg-slate-50"
  >
    <p class="text-medium text-slate-700">{{ taskName }}</p>
    <button
      @click="removeThisTask"
      class="flex h-8 w-8 hover:bg-red-100 rounded-md items-center justify-center text-red-500 font-bold"
    >
      &times;
    </button>
  </div>
</template>
<script>
export default {
  name: "Task",
  props: {
    taskName: String,
    id: Number,
  },
  methods: {
    removeThisTask() {
      this.$emit("removeTask", this.id);
    },
  },
};
</script>
<style></style>
