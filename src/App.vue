<template>
  <div id="app">
    <p>fgh</p>
    <todoList
    v-bind:todos= "todos"
    />
  </div>
</template>

<!--<script>export default {name: "app",components: {}}</script>-->
<script>
  import todoList from '@/components/todoList';
  export default {
    name: 'app',
    data() {
      return {
      todos: [
        { id: 1, title: 'купить хлеб', completed: false },
        { id: 2, title: 'купить молоко', completed: false },
        { id: 3, title: 'выбросить мусор', completed: false },
      ]
    };
    },
    components: {
      todoList
    }
  };
</script>

<style>
#app {
  width: 1200px;
  margin: auto;
  font-family: sans-serif;
  text-align: center;
  font-size: 16px;
}
</style>
