<template>
  <div id="app">
    <Header/>
    <img width="25%" src="./assets/logo.png">
    <h1> Do Something... </h1>
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
    
  </div>
</template>

<script>
import Header from './components/layout/Header'
import Todos from './components/Todos'
import AddTodo from './components/AddTodo'
export default {
  name: "App",
  components: {
    Todos,
    Header,
    AddTodo
  },
   data(){
     return{
 todos:[
      {id:1,title:'Meeting',completed:false},
      {id:2,title:'dinner',completed:true},
      {id:3,title:'Go BTS',completed:false},
      {id:4,title:'Finger Print',completed:true},
      {id:5,title:'On the Jobs',completed:false}
     ]
     }
    
   },
   methods:{
     deleteTodo(id){
       this.todos = this.todos.filter(todo => todo.id !==id)
     },
     addTodo(newTodo){
       this.todos = [...this.todos ,newTodo]
     }
   }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>
