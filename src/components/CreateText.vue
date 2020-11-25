<template>
  <div class="createtext">

    <div class="createtext__title">
      <h2>TodoList</h2>
    </div>

    <div class="createtext__form">
      <input v-model="newTodo" type="text"/>
      <button class="createtext__button" type="submit" @click="addTodo">✔</button>
    </div>

    <div v-for="(newTodo, i) in todos" :key="newTodo.id">

      <div class="todoBox">
        <div class="todoText">
          <span class="todo__id">{{ i+1 }} -- </span>
          <span>{{ newTodo.text }}</span>
        </div>
        <button @click="deleteTodo(i)">✖</button>
      </div>

    </div>
  </div>


</template>

<script>
export default {
  name: "CreateText",
  data() {
    return {
      newTodo: "",
      todos: [],

    }
  },
  methods: {
    addTodo() {
      if (this.newTodo != "") {
        this.todos.push({
          id: this.id,
          text: this.newTodo,
        })
      }
      this.newTodo = ""
    },
    deleteTodo(index) {
      this.todos.splice(index, 1)
    }
  }
}
</script>

<style lang="scss">
.createtext {
  display: flex;
  justify-content: center;
  flex-direction: column;

  &__title {
    text-align: center;
  }

  &__form {
    text-align: center;
  }

  &__button {
    padding: 3px;
  }

  .todoBox {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    padding: 10px;
  }
}
</style>