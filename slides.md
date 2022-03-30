---
theme: default
layout: center
class: text-center
highlighter: shiki
lineNumbers: true
drawings:
  persist: false
title: VueJS Introduction
---

# Mari Belajar VueJS

Intro to VueJS (Directives)

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Yuk ke halaman selanjutnya <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="mt-24">
  <p class="text-sm">*Gunakan Dark Mode di kiri bawah yah untuk hasil maksimal</p>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/slidevjs/slidev" target="_blank" alt="GitHub"
    class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!-- -->

<style>
h1 {
  @apply text-green-400
}
</style>

---

# Isi Pembelajaran

- What is VueJS?
- jQuery vs VueJS
- VueJS Directives
  - v-text
  - v-html
  - v-if
  - v-model
  - v-for
  - v-bind
  - v-on
- VueJS Options API
- VueJS DevTools

<style>
h1 {
  @apply text-green-400
}

ul li {
  @apply ml-5 list-disc
}

ul ul li {
  @apply ml-6 my-0 list-circle
}
</style>

---

# What is VueJS? (I)

Sebuah JS Framework untuk membangun User Interface

- ℹ️ **Modern** - VueJS lebih terbarukan ketimbang jQuery
- ℹ️ **Standard Friendly** - Di bangun di atas standar HTML, CSS, dan JS
- ℹ️ **SPA Friendly** - VueJS mantap untuk membuat projek berbasis Single Page Application
- ℹ️ **Developer Friendly** - Memiliki tingkat kesulitan yang **relatif** mudah ketimbang JS Framework lainnya
- ℹ️ **Selain Itu VueJS juga** - ... ... ... ... ... ... ... 

Ingin baca lebih lanjut mengenai [VueJS](https://vuejs.org/guide/introduction.html#what-is-vue) ?

<!-- -->

<style>
h1 {
  @apply text-green-400
}

li:last-child {
  @apply mb-12
}

a {
  @apply text-green-400 hover:text-green-700 hover:underline
}
</style>

---

# What is VueJS? (II)

- 🎉 **Top 3 FrontEnd JS Framework** 🎉 (Tiga Besar FE JS Framework yang digunakan)*

<div class="min-w-full flex flex-col justify-center items-center">
  <img border="rounded" src="/assets/charts.png" class="w-142">
</div>

*Berdasarkan data dari [State of JS 2021](https://2021.stateofjs.com/en-US/libraries/front-end-frameworks)

<style>
h1 {
  @apply text-green-400;
}

a {
  @apply text-green-400 hover:text-green-700 hover:underline
}
</style>

---

# Vue vs jQuery (I)

<div class="min-w-full h-96 flex flex-col justify-center items-center">
  <p class="text-green-400 italic font-serif">- Kode lebih dari seribu bahasa untuk menjelaskan ini -</p>
  <p class="text-green-400 italic"> WF - 2022</p>
</div>

<style>
  h1 {
    @apply text-green-400
  }
</style>

---

# Vue vs jQuery (II)

<div class="min-w-full h-96 flex flex-col justify-center items-center">
  <p class="text-green-400">- Mari kita liat perbandingannya -</p>
  <p>(dengan membuat aplikasi ToDo List Sederhana)</p>
</div>

<style>
  h1 {
    @apply text-green-400
  }
</style>

---

# Vue vs jQuery (III)

## Aplikasi Todo List

<div class="mt-10">
  <ToDoList />
</div>

<style>
  h1 {
    @apply text-green-400
  }
</style>

---
layout: two-cols
---

# Bedah Kode jQuery
HTML


```html {all|0}
<div id="app">
  <h2>Todo (jQuery)</h2>
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
```

::right::

# Bedah Kode VueJS
HTML

```html {0|3|4-9|18|all}
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
```

<style>
  h1 {
    @apply text-green-400
  }

  pre {
    @apply pr-4
  }
</style>

---
layout: two-cols
---

# Bedah Kode jQuery (II)
JavaScript

```js {all|4-6|8-15|1|all|0}
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
```

::right::

# Bedah Kode VueJS (II)
JavaScript

```js {0|1,14|2-7|8-13|all}
Vue.createApp({
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
}).mount("#app");
```

<style>
  h1 {
    @apply text-green-400
  }

  pre {
    @apply pr-4
  }
</style>

---
layout: center
---

# End of Slides ?

<style>
  h1 {
    @apply text-green-400
  }
</style>

---
layout: center
---

# Fun Fact:
## Slide ini dibuat sepenuhnya menggunakan VueJS 😊

<style>
  h1 {
    @apply text-green-400
  }
</style>