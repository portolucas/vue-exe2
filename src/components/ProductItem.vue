<template>
  <div>
    <h1>{{ item.name }}</h1>
    <p>{{ item.price }}</p>
  </div>
</template>

<script>
export default {
  props: {
    item: Object,
  },
};
</script>

<style scoped>
h1,
p {
  color: black;
}
</style>
