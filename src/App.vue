<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/todos.png">
    <Header/>
    <AddTodo v-on:addElement="addElement"/>
    <Todos v-bind:list_items="list_items"
           v-on:removeTodo="removeTodo"
           />
  </div>
</template>

<script>
import Header from "@/components/header/Header";
import Todos from "@/components/todos/Todos";
import AddTodo from "@/components/todos/AddTodo";

export default {
  name: 'App',
  components: {
    Header,
    Todos,
    AddTodo,
  },
  data() {
    return {
      list_items: [
        {id: 1, text: 'Main', completed: false},
        {id: 2, text: 'Portfolio', completed: false},
        {id: 3, text: 'Blog', completed: false},
        {id: 4, text: 'Home', completed: false},
        {id: 5, text: 'Hello', completed: false}
      ]
    }
  },
  methods: {
    removeTodo(id) {
      this.list_items = this.list_items.filter(t => t.id !== id)
    },
    addElement(todo) {
      todo.id = this.list_items.length + 1
      this.list_items.push(todo)
    },
  }
}
</script>

<style lang="scss">
@import "scss/normalize";
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  width: 50%;
  margin: 20px auto;
  border: 2px solid grey;
  -webkit-box-shadow: 20px 20px 10px 0 rgba(0,0,0,0.65);
  box-shadow: 20px 20px 10px 0 rgba(0,0,0,0.65);
  @media only screen and (max-width: 992px) {
    width: 70%;
  }
  @media only screen and (max-width: 767px) {
    width: 80%;
  }
  @media only screen and (max-width: 567px) {
    width: 90%;
  }
}
</style>
