/* eslint-disable vue/valid-template-root */
<template>
  <v-app>
    <div>
      <form @keyup.enter.prevent="addTodo">
        <v-text-field v-model="title"
                      prepend-icon="mdi-card-plus"
                      label="Todo Title" />
        <v-text-field v-model="date"
                      prepend-icon="mdi-clock"
                      label="When do you do by?" />
      </form>
      <h4 class="total-tasks">Total Tasks: {{todos.length}}</h4>
      <!-- All Deleteボタンを作りたい -->
      <div v-for="(todo,index) in todos"
                  :key="todo.id"
                  class="todo-item">
        <div class="todo-item-left">
          <input  type="checkbox"
                  :class="completed"
                  @click="check">
          {{ todo.title + '(' + todo.date +')'}}
          <hr>
        </div>
        <p class="remove-item" @click="removeTodo(index)">
          <span class="material-icons">
            ×
          </span>
        </p>
      </div>
    </div>
  </v-app>
</template>


<!-- ↓内容の変更をstoreで管理したい -->


<script>
export default {
  name: 'todo-list',
  data() {
    return {
      idForTodo: 1,
      title:'',
      date:'',
      todos:[]
    }
  },
  methods: {
    addTodo() {
      if(this.title.trim() == 0 || this.date.trim() == 0){
        return
      }
      this.todos.push({
        id: this.idForTodo,
        title: this.title,
        date: this.date,
        completed: false,
      }),
      this.title = '',
      this.date = '',
      this.idForTodo ++
    },

    removeTodo(index) {
      if(confirm('Are you sure OK?')){
        this.todos.splice(index, 1)
      }
    },

    check() {
      if(this.todo.completed) {
        this.todos.title.classList.add('completed')
      }
    },

  }
}
</script>

<style scoped>
  input {
    border: 1px solid #999;
    border-radius: 5px;
    padding: 5px 10px;
  }

  div {
    width: 600px;
    margin: 0 auto;
    /* background-color: #fdf; */
  }

  .todo-input {
    width: 100%;
    padding: 10px 18px;
    font-size: 18px;
    margin-bottom: 18px;
  }

  .todo-item {
    margin-bottom: 12px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    /* background-color: #fdf; */
  }

  .remove-item {
    cursor: pointer;
    margin-left:14px;
  }
  .remove-item:hover {
    color: red;
  }

  .completed {
    text-decoration: line-through;
    color: red;
  }

  .total-tasks {
    margin: 10px 0;
  }
</style>