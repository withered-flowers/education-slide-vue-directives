<script>
export default {
  data() {
    return {
      customImageUrl1: "https://via.placeholder.com/128",
      customImageUrl2: "https://placekitten.com/128",
    };
  },
};
</script>

<template>
  <div>
    <img v-bind:src="customImageUrl1" alt="A Placeholder" />
    <div style="padding-top: 0.25rem; padding-bottom: 0.25rem">&nbsp;</div>
    <img :src="customImageUrl2" alt="A Kitten" />
  </div>
</template>
