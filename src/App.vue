<template lang="">
  <div>likes: {{ likes }}</div>
  <button @click="likes++">+</button>
  <button @click="likes--">-</button>
</template>
<script>
export default {
  data() {
    return {
      likes: 0,
    };
  },
};
</script>
<style lang=""></style>
