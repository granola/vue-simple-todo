<template>
  <div class="card-root">
    <p :hidden="isEdit">{{ todo.title }}</p>
    <input v-model="todo.title" :hidden="!isEdit" @keyup.enter="edit" />
    <p @click="isEdit = true">編集</p>
    <p @click="deleteTodo(todo.id)">削除</p>
  </div>
</template>

<script lang="ts">
export default {
  props: ["todo", "editTodo", "deleteTodo"],
  data: function() {
    return {
      isEdit: false
    };
  },
  methods: {
    edit: function() {
      this.editTodo(this.todo.id, this.todo.title);
      this.isEdit = false;
    }
  }
};
</script>

<style scoped>
.card-root {
  width: 80%;
  margin: 30px auto;
  background-color: #2114150d;
}
</style>
