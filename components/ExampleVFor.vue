<script>
export default {
  data() {
    return {
      customLooper: ["Options API", "Directives", "v-xxx"],
    };
  },
};
</script>

<template>
  <div>
    <p>Apa yang sudah dipelajari?</p>
    <ul>
      <li v-for="data in customLooper">
        {{ data }}
      </li>
    </ul>
  </div>
</template>
