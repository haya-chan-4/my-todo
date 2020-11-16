
<template>
  <div id="App" class="container">
    <!-- ↓をコンポーネント化したい -->
    <div class="header">
      <img src="./assets/logo.png" class="logo">
      <h1>{{headerName}}</h1>
    </div>
    <!-- ↑をコンポーネント化したい -->
    <todoList />
  </div>
</template>

<script>

import TodoList from './components/TodoList.vue';


export default {
  components: {
    TodoList,
  },
  name: 'App',
  data: () => ({
    //
    headerName: 'Todo App'
  }),
};
</script>

<style>
  * {
    box-sizing: border-box;
    background-color: rgb(246, 224, 246);
  }

  .container {
    max-width: 400px;
    margin: 0 auto;
  }

  .header {
    display: flex;
    flex-direction: row;
    align-items: center;
    text-align: center;
  }

  #app {
    color: #2c3e50;
    margin-top: 20px;
    font-size: 24px;
  }

  .logo {
    display: block;
    margin: 20px 40px;
    height: 75px;
  }

  h1 {
    text-align: left;
    font-family: Georgia, 'Times New Roman', Times, serif;
  }
</style>