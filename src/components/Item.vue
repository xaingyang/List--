<template>
      <li @mouseenter="isShow=true" @mouseleave="isShow=false" :class="{myClass:isShow}">
          <label>
            <input type="checkbox" :checked="todo.isOver" @click="updateO"/>
            <!-- <input type="checkbox" v-model="isChecked"/> -->
            <span>{{todo.content}}</span>
          </label>
          <button class="btn btn-danger" v-show="isShow" @click="deleteO">删除</button>
      </li>
</template>

<script>
export default {
  name: '',
  props:{
      todo:Object,
      index:{
          type:Number,
          default:0
      },
      updateOne:Function,
      deleteOne:Function
  },
  data() {
      return {
          isShow:false
      }
  },
  computed:{
      isChecked:{
          get(){
              return this.todo.isOver
          },
          set(){

          }
      }
  },
  methods:{
      updateO(){
        this.updateOne(this.index)
      },
      deleteO(){
        this.deleteOne(this.index)
      }
  }
}
</script>

<style scoped>
/*item*/
li {
  list-style: none;
  height: 36px;
  line-height: 36px;
  padding: 0 5px;
  border-bottom: 1px solid #ddd;
}

li label {
  float: left;
  cursor: pointer;
}

li label li input {
  vertical-align: middle;
  margin-right: 6px;
  position: relative;
  top: -1px;
}

li button {
  float: right;
  /* display: none; */
  margin-top: 3px;
}

li:before {
  content: initial;
}

li:last-child {
  border-bottom: none;
}

.myClass{
    background-color:bisque;
    /* opacity: 0.3; */
}
</style>
