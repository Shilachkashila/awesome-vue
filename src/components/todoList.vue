<template lang="html">
  <div>
    <ul>
      <todoItem
      v-for="(todo, i) in todos" :key="todo.title"
      :todo="todo"
      :index="i"
      v-on:remov-todo="removTodo"
      />
    </ul>
  </div>
</template>

<script>
import todoItem from '@/components/todoItem';
export default {
  props: ['todos'],//данные от родителя к потомкам - с помощью пропс и директивы v-bind
  components: {
    todoItem
  },
  //данные от потомка к родителю v-on  и методс но это не точно :)
  methods: {
    removTodo(id) {
      this.$emit( 'remov-todo', id )
      //console.log(id)
    }
  }
};
</script>

<style lang="css" scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
}
</style>
