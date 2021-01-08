<template>
  <form class="add-form" v-on:submit.prevent="addElement">
    <label class="add-form__label">Добавить к списку</label>
    <input class="add-form__input" type="text" placeholder="Добавить..." v-model="text">
    <button class="add-form__button" type="submit">Добавить</button>
  </form>
</template>

<script>
export default {
name: "AddTodo",
  data() {
    return {text: ''}
  },
  methods: {
    addElement() {
      if (this.text.trim()) {
        const newTodo = {
          id: 0,
          text: this.text,
          completed: false,
        }
        this.$emit('addElement', newTodo)
        this.text = ''
      }
    }
  }
}
</script>

<style scoped lang="scss">
.add-form {
  padding: 20px 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: grey;
  &__label {
    margin-bottom: 20px;
  }
  &__input {
    height: 40px;
    padding: 5px;
    margin-bottom: 10px;
  }
  &__button {
    background-color: #0dee0f;
    height: 30px;
    width: 100px;
    cursor: pointer;
  }
}

</style>