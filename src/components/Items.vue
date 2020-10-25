<template>
  <div class="container">
    <ul>
      <h2>the item</h2>
      <li v-for="(value, index) in listdata" :key="index">{{value.item}}</li>
    </ul>
    <ul>
      <h2>the color</h2>
      <li v-for="(value, index) in listdata" :key="index">{{value.color}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    listdata: Array
  }
};
</script>

<style scoped>
.container {
  position: relative;
  display: flex;
  justify-content: center;
  margin-top: -40px;
}
ul {
  position: relative;
  display: flex;
  flex-direction: column;
  list-style: none;
  text-align: left;
}
li {
  list-style: none;
  text-align: center;
}
</style>
