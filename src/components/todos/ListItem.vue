<template>
  <li class="todos-list__item">
    <span class="todos-list__check" v-bind:class="{done: item.completed}">
      <input type="checkbox"
             v-on:change="item.completed = !item.completed">
      <strong class="todos-list__text">{{item.id}} {{item.text}}</strong>
    </span>
    <button class="todos-list__button"
            v-on:click="$emit('removeTodo', item.id)">&#10060;</button>
  </li>
</template>

<script>
export default {
  name: "ListItem",
  props: {
    item: {
      type: Object,
      required: true,
    }
  },
}
</script>

<style scoped lang="scss">
.todos-list {
  &__item {
    height: 60px;
    margin-bottom: 20px;
    border: 1px solid gray;
    cursor: pointer;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 10px;
  }
  &__item:hover {
    background-color: #0dee0f;
  }
  &__text {
    margin: 0 10px;
  }
  &__button {
    border-radius: 50%;
    background-color: ivory;
    cursor: pointer;
  }
  &__button:focus {
    border-radius: 50%;
    outline: none;
  }
}
.done {
  text-decoration: line-through;
}
</style>