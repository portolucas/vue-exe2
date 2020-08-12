<template>
  <div>
    <li v-for="item in list" v-bind:key="item.name">
      <ProductItem :item="item" />
    </li>
  </div>
</template>

<script>
import ProductItem from "./ProductItem";

export default {
  components: {
    ProductItem,
  },
  props: {
    list: Array,
  },
  created() {
    console.log(this.list);
  },
};
</script>

<style scoped>
li {
  color: black;
  list-style: none;
}
</style>
