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
    <p>Dengan shorthand: {{ exampleData }}</p>
  </div>
</template>
