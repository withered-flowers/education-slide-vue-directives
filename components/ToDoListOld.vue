<script>
import $ from "jquery";

const todos = ["Belajar jQuery", "Belajar VueJs"];

$(function () {
  todos.forEach(function (todo) {
    $("#todoList").append(`<li>${todo}</li>`);
  });

  $("#formTodo").on("submit", function (event) {
    event.preventDefault();

    const newTodo = $("#todoValue").val();

    $("#todoList").append(`<li>${newTodo}</li>`);
    $("#todoValue").val("");
  });
});
</script>

<template>
  <div id="app">
    <h2>Todo</h2>
    <form method="post" id="formTodo">
      <input
        type="text"
        placeholder="Title"
        id="todoValue"
        class="p-2 rounded-xl text-gray-700"
      />
      <button
        type="submit"
        class="ml-2 p-3 rounded-xl dark:bg-green-400 dark:text-slate-700"
      >
        Tambah
      </button>
    </form>
    <ul id="todoList"></ul>
  </div>
</template>
