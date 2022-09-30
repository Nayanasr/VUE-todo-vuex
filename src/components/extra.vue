<template>

    <h1>🚩TODO APP🚩</h1>
    
     <div>
       <input type="text" v-model="todo" placeholder="ADD TODO"/>
       <button style="color:green" @click="addTodo">ADD</button>
     </div>

     <div v-for="todo in todos" v-bind:key="todo.id">{{ todo.text }}
     <button style="color:red" @click="removeTodo(todo.id)">REMOVE</button>
    </div>

</template>

<script>

export default {
  name: 'App',
  components: {
  },
  data() {
    return {
      todo: '',

      todos: [
        {
          id: Math.random(),
          text: 'hello',
        },
        {
          id: Math.random(),
          text: 'world',
        },
      ],
    };
  },
  methods: {
    removeTodo(todoId){
     this.todos = this.todos.filter((todo) => todo.id !== todoId);
    },

    addTodo(){
      if(this.todo.length === 0) {
        return;
      } else {
         this.todos.push({
          id: Math.random(),
          text: this.todo,
        });
      }
    }
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
