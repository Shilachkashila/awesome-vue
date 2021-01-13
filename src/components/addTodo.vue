<template>
<form
v-on:submit.prevent="onSubmit">
  <input type="text" v-model="title">
  <button type="submit" name="button">
  add
  </button>
</form>
</template>

<script>
export default {
  data() {
    return {
      title: ''
    }
  },
methods: {
  onSubmit() {
  console.log('submit', this.title);
  if (this.title.trim()) {
  const newTodo = {
    id: Date.now(),
    title: this.title,
    completed: false
  }
  this.$emit('add-todo', newTodo)
  }
}
}
}
</script>
<style scoped>
form {
  margin-bottom: 1rem;
}
input {
  box-sizing: border-box;
  width: 70%;
  height: 2rem;
  border: 1px solid #9966ff;
  background-color: #ccccFF;
}
button {
  height: 2rem;
  border: 1px solid #9966ff;
}
</style>
