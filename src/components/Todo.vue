<template>
  <div v-bind:class="{ 'completed': todo.completed }">
    <p v-on:click="markComplete">{{ todo.title }}</p>
    <input type="text" v-model="todo.title">
    <button @click="$emit('delete-todo', todo.id)">Delete</button>
        <button @click="$emit('edit-todo', todo.title)">Edit</button>
  </div>
</template>
<script>
export default {
  name: 'Todo',
  props: [
    "todo"
  ],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed
    }

  }
}
</script>
<style scoped>
  .completed {
    text-decoration: line-through;
  }
</style>