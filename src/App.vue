<template>
  <div class="todo-container">
    <div class="todo-wrap">
      <!-- <Header :addTodo="addTodo"/> -->
      <Header @addTodo="addTodo"/>
      <List :todos="todos" :updateOne="updateOne" :deleteOne="deleteOne"/>
      <Footer :todos="todos" :AllCheck="AllCheck" :deleteAll="deleteAll"/>
    </div>
  </div>
</template>

<script>
import Header from './components/Header'
import Footer from './components/Footer'
import List from './components/List'

export default {
  name: '',
  components:{
    Header,
    Footer,
    List
  },
  data() {
    return {
      todos:[
        {id:1,content:'追剧',isOver:false},
        {id:2,content:'打球',isOver:true},
        {id:3,content:'睡觉',isOver:false},
        {id:4,content:'喝酸奶',isOver:true},
      ]
    }
  },
  methods: {
    addTodo(todo){
      return this.todos.unshift(todo)
    },
    updateOne(index){
      this.todos[index].isOver=!this.todos[index].isOver
    },
    deleteOne(index){
      this.todos.splice(index,1)
    },
    AllCheck(val){
      this.todos.forEach(item=>item.isOver=val)
    },
    deleteAll(){
      this.todos=this.todos.filter(item=>!item.isOver)
    }
  },
}
</script>

<style scoped>
/*app*/
.todo-container {
  width: 600px;
  margin: 0 auto;
}
.todo-container .todo-wrap {
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}

/*header*/
.todo-header input {
  width: 560px;
  height: 28px;
  font-size: 14px;
  border: 1px solid #ccc;
  border-radius: 4px;
  padding: 4px 7px;
}

.todo-header input:focus {
  outline: none;
  border-color: rgba(82, 168, 236, 0.8);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 8px rgba(82, 168, 236, 0.6);
}
</style>
