<template>
    <div>
        <h1> <router-link to="/v-bind">v-bind</router-link> with hover</h1>
         <span v-bind:title="message">
             Passez votre souris sur moi pendant quelques secondes
             pour voir mon titre lié dynamiquement !
        </span>
        <h1>v-if Seen if data is true, v-else data is false</h1>
        
        <div v-if="seen">
          <p>This is a v-if. You see me cause seen===true</p>
          <button @click="changeValue">Change to false </button>
        </div>

        <div v-else>
          <p>This is a v-else. You see me cause seen===false</p>
          <button @click="changeValue">Change to true</button>
        </div>
        <h1>Display in todos with a v-for</h1>
         <ol>
            <li v-for="todo in todos" :key="todo">{{ todo.text }}</li>
        </ol>
         <h1>Reverse message</h1>
          <p>{{ msg }}</p>
         <button v-on:click="reverseMessage">Reverse message</button>
        <input v-model="msg">

        {{msg.split('').reverse().join('')}}
        
          <h1>Parent to child with props</h1>
        <div class="container">
      <ul>
        <h2>the item</h2>
        <li v-for="(value, index) in listdata" :key="index">{{value.item}} </li>
      </ul>
      <ul>
        <h2>the color</h2>
        <li v-for="(value, index) in listdata" :key="index">{{value.color}} </li>
      </ul> 
      </div>
    </div>
</template>

<script>
export default {
   name: 'Main',
   props: {
    'listdata': Array,
  },
    data() {
        return { 
          message: 'Vous avez affiché cette page le ' + new Date().toLocaleString(),
          seen: true, 
          todos: [
            { text: 'Apprendre JavaScript' },
            { text: 'Apprendre Vue' },
            { text: 'Créer quelque chose de génial' }
          ],
          msg: 'Hello Vue.js !'
        }
    },
    methods: {
        changeValue(){
            console.log(this.seen)
            if(this.seen ==true){
                return this.seen = false
                }
            else{
                return this.seen = true
            }    
        },
        reverseMessage: function () {
            this.msg = this.msg.split('').reverse().join('')
        }
    },
}
</script>

<style scoped>
.container{
  position: relative;
  display: flex;
  justify-content: center;
  margin-top: -40px;
}

ul{
  position: relative;
  display: flex;
  flex-direction: column;
  list-style: none;
  text-align: left;
}

li{
  list-style: none;
  text-align: center;
}
</style>
