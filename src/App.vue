<template>
  <div id="app">
    <ProductList :list="list" />
    <ProductForm :changeValue="changeValue" />
    <h2>O número total de produtos é: {{ product }}</h2>
  </div>
</template>

<script>
import ProductList from "./components/ProductList";
import ProductForm from "./components/ProductForm";

export default {
  name: "App",
  components: {
    ProductList,
    ProductForm,
  },
  data() {
    return {
      list: [{ name: "iPhone", price: "21.000,000" }],
    };
  },
  computed: {
    product: {
      get: function() {
        return this.list.length;
      },
      set: function(newValue) {
        this.list = this.list.concat({
          name: newValue.name,
          price: newValue.price,
        });
      },
    },
  },
  methods: {
    changeValue(newValue) {
      this.product = newValue;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
