<template>
  <div class="app">
    <ul>
      <li
        v-for="todo in todos"
        v-bind:key="todo.id"
        :class="{ check: !feito, 'check-feito': feito }"
      >
        <span>{{ todo.text }}</span>
        <input type="checkbox" @click="terminar" />
      </li>
    </ul>
    <div class="inputs">
      <input type="text" placeholder="To-do" v-model="text" />
      <div class="buttons">
        <button v-on:click="addTodo(text)">Adicionar</button>
        <button v-on:click="removeTodos()">Remover Todas</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Todo",
  data() {
    return {
      todos: [{ id: 1, text: "Aprender VueJS" }],
      feito: false,
    };
  },
  methods: {
    addTodo(text) {
      if (text !== "") {
        this.todos.push({
          id: this.todos.length + 1,
          text,
        });
      }
    },
    removeTodos() {
      this.todos = [];
    },
    terminar() {
      this.feito = !this.feito;
    },
  },
};
</script>

<style>
#app{
    display: flex; 
    flex-direction: column;
    flex-wrap: wrap;
    align-items: center;
    width: 60%;
    padding: 5%; margin: 5% auto 5% auto;
    box-shadow: rgb(190, 190, 190) 1px 1.5px 8px 1.5px;
    border-radius: 10px;
}
input {
  padding: 2%;
  margin: 2%;
}
input:hover {
    background: rgb(241, 240, 255);
}
li {
    list-style: none;
}
.buttons{
    display: flex;
    justify-content: space-around;
    width: 100%;
}
button {
  padding: 4%;
  margin: 2%;
  background: rgb(61, 19, 251);
  color: whitesmoke;
  border: none;
  border-radius: 5px;
  box-shadow: rgb(173, 173, 173) 0.5px 1px 4px 0.5px;
}
button:hover {
  scale: 1.05;
  background: rgb(34, 12, 133);
  color: white;
}
.check {
  text-decoration: none;
}
.check-feito {
  text-decoration: line-through;
  font-weight: 600;
}
</style>