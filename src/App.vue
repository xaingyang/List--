<template>
  <div>
      <Son>
          <!-- 匿名插槽 -->
          <template>
              <button>点我</button>
          </template>

          <!-- 具名插槽 -->
          <template slot="xxx">
              <a href="https://www.baidu.com">
                  我是父组件
              </a>
          </template>

          <template slot="yyy">
              <a href="https://www.baidu.com">
                  我是父组件2,具名插槽可以有多个
              </a>
          </template>

          <!-- 作用域插槽 -->
          <ScopedChild :stars="stars">
              <!-- <h2>作用域插槽是父组件的数据,传给子组件内进行使用,传递的数据是可以带格式的数据,若果格式变动,后期项目子组件是封装好的,不好改动,可以在父组件改动数据格式</h2> -->
              <template slot-scope="{item}">
                  <span v-if="item.isOver" style="color:red">
                      >{{item.name}}
                  </span>
              </template>
          </ScopedChild>
      </Son>


  </div>
</template>

<script>
import ScopedChild from './components/ScopedChild'
import Son from './components/son'
export default {
  name: '',
  data(){
      return {
          stars:[
              {id:1,name:'谢可寅',age:23,isOver:true},
              {id:2,name:'老爷爷',age:83,isOver:false},
              {id:3,name:'俊霞',age:22,isOver:false},
              {id:4,name:'小虎',age:13,isOver:true}
          ]
      }
  },
  components:{
      ScopedChild,
      Son
  }
}
</script>

<style scoped>

</style>
