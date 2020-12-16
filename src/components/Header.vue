<template>
  <section class="jumbotron">
      <h3 class="jumbotron-heading">搜索github的用户</h3>
      <div>
        <input type="text" placeholder="请输入你要搜索的内容" v-model="keyword"/>
        <button @click="search">搜索</button>
      </div>
    </section>
</template>

<script>
export default {
  name: '',
  data() {
      return {
          keyword:''
      }
  },
  methods:{
      search(){
          let keyword=this.keyword
          if(keyword.trim()){
               this.$bus.$emit('searchAjax',keyword)
          }else{
              alert('关键字格式不合法')
          }

          this.keyword=""
      }
  }
}
</script>

<style scoped>

</style>
