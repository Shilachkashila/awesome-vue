<template lang="html">
  <div>
    <ul>
      <todoItem
      v-for="todo in todos"
      :todo="todo"
      :key="todo.id"
      />
    </ul>
  </div>
</template>

<script>
import todoItem from '@/components/todoItem';
export default {
  props: ['todos'],
  components: {
    todoItem
  }
};
</script>

<style lang="css" scoped>
</style>
