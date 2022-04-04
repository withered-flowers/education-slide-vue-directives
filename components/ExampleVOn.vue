<script>
export default {
  data() {
    return {
      customValue: "Masih Kosong nih",
    };
  },
  methods: {
    clickMe() {
      this.customValue === "Masih kosong nih"
        ? (this.customValue = "Makin ngerti VueJS coy")
        : (this.customValue = "Masih kosong nih");
    },
  },
};
</script>

<template>
  <div>
    <p>{{ customValue }}</p>
    <button
      v-on:click="clickMe"
      class="bg-gray-200 hover:bg-gray-400 py-3 px-4 text-slate-700 rounded-xl"
    >
      Tekan Aku
    </button>
  </div>
</template>
