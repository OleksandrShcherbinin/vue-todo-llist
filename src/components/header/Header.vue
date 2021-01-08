<template>
  <div class="todos" id="todo">
    <h2 class="todos__title">My TODO List</h2>
  </div>
</template>

<script>
export default {
  name: "Header"
}
</script>

<style scoped lang="scss">
.todos {
  margin: 0 auto;
  width: 100%;
  min-height: 200px;
  background-color: #42b983;
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
  &__title {
    text-align: center;
    word-break: break-word;
  }
}
</style>