<template>
  <div id="App" class="container">
    <v-app>
      <Header />
      <!-- <Form /> -->
      <TodoList />
    </v-app>
  </div>
</template>

<script>
import TodoList from './components/TodoList.vue';
import Header from './components/Header.vue';
// import Form from './components/Form.vue';

export default {
  components: {
    TodoList,
    Header,
    // Form,
  },
  name: 'App',
  data: () => ({
    //
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

  #app {
    color: #2c3e50;
    margin-top: 20px;
    font-size: 24px;
  }
</style>