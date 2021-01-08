<template>
  <div class="todos" id="list">
    <ul class="todos-list">
      <List_item
          v-for="item of list_items"
          v-bind:item="item"
          v-on:removeTodo="removeTodo"/>
    </ul>
  </div>
</template>

<script>
import List_item from "@/components/todos/ListItem";

export default {
  name: "Todos",
  props: ['list_items'],
  components: {List_item},
  methods: {
    removeTodo(id) {
      this.$emit('removeTodo', id)
    }
  }
}
</script>

<style scoped lang="scss">
.todos {
  margin-top: 0;
  background-color: #0f6674;
  color: white;
  font-weight: 900;
  display: flex;
  flex-direction: column;
  align-items: center;
  &-list {
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
}

</style>