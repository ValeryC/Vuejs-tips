<template>
    <div>
        <Home :listdata="items" />
        <router-view />
    </div>
</template>

<script>
import Home from './components/Home.vue'

export default {
  name: 'App',
  components: {
    Home
  },
  data() {
      return { 
          items:[         
          {item: 'pencil', color:'blue'},
          {item: 'pencil2', color:'red'},
          {item: 'pencil3', color:'orange'},
          {item: 'pencil4', color:'green'},
          {item: 'pencil5', color:'brown'},
          ],
          }
    }
  }

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
