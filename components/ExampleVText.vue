<script>
export default {
  data() {
    return {
      exampleData: "Halo VueJS",
    };
  },
};
</script>

<template>
  <div>
    <p v-text="`Dengan v-text: ` + exampleData"></p>
    <p>Dengan interpolation: {{ exampleData }}</p>
  </div>
</template>
