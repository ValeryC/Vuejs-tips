<template>
  <div>
    <h1>
      <router-link to="/vbind">v-bind</router-link>with hover
    </h1>
    <span v-bind:title="message">
      Passez votre souris sur moi pendant quelques secondes
      pour voir mon titre lié dynamiquement !
    </span>
    <h1>v-if Seen if data is true, v-else data is false</h1>

    <div v-if="seen">
      <p>This is a v-if. You see me cause seen===true</p>
      <button @click="changeValue">Change to false</button>
    </div>

    <div v-else>
      <p>This is a v-else. You see me cause seen===false</p>
      <button @click="changeValue">Change to true</button>
    </div>
    <h1>Display in todos with a v-for</h1>
    <ol>
      <li v-for="todo in todos" :key="todo">{{ todo.text }}</li>
    </ol>
    <ol>
      <li v-for="value in object" :key="value">{{value}}</li>
    </ol>
    <h1>Reverse message</h1>
    <p>{{ msg }}</p>
    <button v-on:click="reverseMessage">Reverse message</button>
    <input v-model="msg">
    {{msg.split('').reverse().join('')}}
    <h1>Send data from Parent to child with props</h1>
    <!-- import component Item -->
    <Items :listdata="items"/>

    <h1>Send data from child to Parents with emit</h1>

    <Emit @changeMsg="setMessage" :msg="welcomeMsg"/>
    <h2>{{ welcomeMsg }}</h2>
  </div>
</template>

<script>
import Items from "../components/Items.vue";
import Emit from "../components/Emit.vue";
export default {
  name: "Main",
  components: { Items, Emit },
  data() {
    return {
      welcomeMsg: "This is the principal message to change",
      msg: "Hello Vue.js !",
      message: "Vous avez affiché cette page le " + new Date().toLocaleString(),
      seen: true,
      object: { tool: "hammer", couleur: "blue", animal: "butterfly" },
      todos: [
        { text: "Apprendre JavaScript", couleur: "blue", animal: "butterfly" },
        { text: "Apprendre Vue" },
        { text: "Créer quelque chose de génial" }
      ],
      items: [
        { item: "pencil", color: "blue" },
        { item: "pencil2", color: "red" },
        { item: "pencil3", color: "orange" },
        { item: "pencil4", color: "green" },
        { item: "pencil5", color: "brown" }
      ]
    };
  },
  methods: {
    changeValue() {
      console.log(this.seen);
      if (this.seen == true) {
        return (this.seen = false);
      } else {
        return (this.seen = true);
      }
    },
    reverseMessage: function() {
      this.msg = this.msg
        .split("")
        .reverse()
        .join("");
      console.log(this.msg);
    },

    setMessage(msg) {
      this.welcomeMsg = msg;
    }
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
