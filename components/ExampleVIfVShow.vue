<script>
export default {
  data() {
    return {
      isTouched: true,
    };
  },
};
</script>

<template>
  <div>
    <div>
      <input type="checkbox" v-model="isTouched" id="checkOne" class="mr-2" />
      <label for="checkOne">Is Touched?</label>
    </div>
    <p v-if="isTouched">Sebuah Tulisan dengan v-if</p>
    <p v-show="!isTouched">A text with v-show</p>
  </div>
</template>
