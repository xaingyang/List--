<template>
  <div class="todo-header">
        <input type="text" placeholder="请输入你的任务名称，按回车键确认" v-model="content" @keyup.enter="addT"/>
  </div>
</template>

<script>
export default {
  name: '',
  data(){
      return {
          content:''
      }
  },
//   props:{
//       addTodo:{
//           type:Function,
//           required:true
//         //   type:Number,
//         //   required:true,  //代表必须传值
//         //   default:10      //代表如果没有传值，就默认值为10
//       }
//   },
  methods:{
      addT(){
          let {content}=this
          if(content.trim()){
              let id=Date.now()
              let isOver=false
              let obj={
                  id,
                  content,
                  isOver
              }
            //   this.addTodo(obj)
            this.$emit('addTodo',obj)
          }else{
              alert('请输入合法的内容')
          }
      }
  }
}
</script>

<style scoped>
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
