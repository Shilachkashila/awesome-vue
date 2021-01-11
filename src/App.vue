<template>
  <div id="app">
    <title-grey
    :titleG="titlesGr1"
    />
    <!-- компонент используется как пользовательский тег с тем же названием. Здесь <todoList/>  -->
    <todo-list
    v-bind:todos= "todos"
    />
    <title-grey
    :titleG="titlesGr2"
    />
  </div>
</template>

<!--<script>export default {name: "app",components: {}}</script>-->
<script>
  import todoList from '@/components/todoList';//импорт компонента на эту страницу
  //по пути указаному после from "@" - это папка src
  import titleGrey from '@/components/titleGrey';
  export default {
  name: 'app',
  data() {
    //
    return {
    todos: [
      { id: 1, title: 'купить хлеб', completed: false, },
      { id: 2, title: 'купить молоко', completed: false, },
      { id: 3, title: 'выбросить мусор', completed: false, },
    ],
      titlesGr1: 'сделать сегодня',
      titlesGr2: 'доделать завтра',
  };
  },
    //регистрируем компонент в поле компонентс указывая имя: ключ
    components: {
      todoList,//здесь имя:ключ todoList:todoList сократили потому, что они одинаковые
      titleGrey
    }
  };
</script>

<style>
#app {
  max-width: 1200px;
  margin: auto;
  font-family: sans-serif;
  text-align: center;
  font-size: 16px;
}
</style>
