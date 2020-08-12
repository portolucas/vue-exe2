<template>
  <div>
    <form @submit.prevent="onFormSubmit">
      <p>
        <label>Name:</label>
        <input type="text" v-model="name" />
      </p>
      <p>{{ nameErrorMsg }}</p>

      <p>
        <label>Price:</label>
        <input type="number" v-model="price" />
      </p>
      <button type="submit">Send</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      price: "",
      nameErrorMsg: "",
    };
  },
  props: {
    changeValue: Function,
  },
  watch: {
    name() {
      if (this.name.length >= 15) {
        this.nameErrorMsg =
          "O nome do produto não pode ultrapassar os 15 caracteres";
      } else {
        this.nameError = "";
      }
    },
  },
  methods: {
    onFormSubmit() {
      this.changeValue({
        name: this.name,
        price: this.price,
      });
    },
  },
};
</script>
