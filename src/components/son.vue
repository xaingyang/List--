<template>
  <div>
      <h2>妈呀</h2>
      <slot>
          <span>嘿嘿</span>
      </slot>

      <slot name="xxx">
          <h2>我是子组件,如果父组件的具名插槽有传过来东西,那么我就会被覆盖,我是个默认值,父组件没传东西,我就显示出来了</h2>
      </slot>

      <slot name="yyy">
          <h2>我是子组件2,如果父组件的具名插槽有传过来东西,那么我就会被覆盖,我是个默认值,父组件没传东西,我就显示出来了</h2>
      </slot>
  </div>
</template>

<script>
export default {
  name: '',
}
</script>

<style scoped>

</style>
