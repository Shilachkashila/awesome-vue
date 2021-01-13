<template>
  <div id="app">
    <title-grey
    :titleG="titlesGr1"
    />
    <add-todo
    v-on:add-todo= "addTodo"
    />
    <!-- компонент используется как пользовательский тег с тем же названием. Здесь <todoList/>  -->
    <todo-list
    v-bind:todos= "todos"
    v-on:remov-todo= "removTodo"
    />
    <title-grey
    :titleG="titlesGr2"
    />
    <!-- <todo-list
    v-bind:todos= "todos"
    v-on:remov-todo= "removTodo"
    />
    <title-grey
    :titleG="titlesGr2"
    />
    <todo-list
    v-bind:todos= "todos"
    v-on:remov-todo= "removTodo"
    />-->
  </div>
</template>

<!--<script>export default {name: "app",components: {}}</script>-->
<script>
  import todoList from '@/components/todoList';//импорт компонента на эту страницу
  //по пути указаному после from "@" - это папка src
  import titleGrey from '@/components/titleGrey';
  import addTodo from '@/components/addTodo';
  export default {
  name: 'app',
  data() {
    return {
    todos: [],
      titlesGr1: 'сделать сегодня',
      titlesGr2: 'доделать завтра',
  };
  },
    //регистрируем компонент в поле компонентс указывая имя: ключ
    components: {
      todoList,//здесь имя:ключ todoList:todoList сократили потому, что они одинаковые
      titleGrey,
      addTodo,
    },
    mounted() {
      //do something after mounting vue instance
      fetch('https://jsonplaceholder.typicode.com/todos?_limit=3')
      .then(response => response.json())
      .then(json =>
      this.todos = json)
    },
    methods: {
    removTodo(id) {
        this.todos = this.todos.filter( t => t.id !== id )
      },
    addTodo(todo) {
      this.todos.push(todo)
    }
    }
  };
</script>

<style>
#app {
  padding: 0;
  margin: 0;
  max-width: 1200px;
  margin: auto;
  font-family: sans-serif;
  text-align: center;
  font-size: 16px;
}
* {
  padding: 0;
}
</style>
