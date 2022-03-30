<script>
export default {
  data() {
    return {
      todos: ["Belajar jQuery", "Belajar VueJS"],
      todoValue: "",
    };
  },
  methods: {
    submitForm() {
      this.todos.push(this.todoValue);
      this.todoValue = "";
    },
  },
};
</script>

<template>
  <div id="app">
    <h2>Todo (Vue)</h2>
    <form method="post" v-on:submit.prevent="submitForm">
      <input
        type="text"
        placeholder="Title"
        v-model="todoValue"
        class="p-2 rounded-xl text-gray-700"
      />
      <button
        type="submit"
        class="ml-2 p-3 rounded-xl dark:bg-green-400 dark:text-slate-700"
      >
        Tambah
      </button>
    </form>
    <ul>
      <li v-for="todo in todos">{{ todo }}</li>
    </ul>
  </div>
</template>
