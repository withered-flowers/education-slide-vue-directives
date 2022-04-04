<script>
export default {
  data() {
    return {
      customDataText: "",
    };
  },
};
</script>

<template>
  <div>
    <input
      type="text"
      v-model="customDataText"
      placeholder="Masukkan input"
      class="p-2 rounded-xl text-gray-700"
    />
    <p>Tulisan dari input ini adalah: {{ customDataText }}</p>
  </div>
</template>
