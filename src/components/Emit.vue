<template>
  <div class="hello">
    <h2>{{ msg }}</h2>
    <br>
    <div class="container">
      <input class="input" type="text" v-model="input">
      <br>
      <br>
      <button @click="changeMsg">Click to change welcome message</button>
    </div>
  </div>
</template>

    <script>
/* eslint-disable */
export default {
  name: "Emit",
  data() {
    return {
      input: ""
    };
  },
  props: {
    msg: String
  },
  methods: {
    changeMsg() {
      this.$emit("changeMsg", this.input);
      console.log("message emit from child component");
    }
  }
};
</script>
    <!-- Add "scoped" attribute to limit CSS to this component only -->
    <style scoped>
.hello {
  text-align: center;
}
</style>