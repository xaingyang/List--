<template>
  <div>
      <ul>
          <li v-for="(item,index) in stars" :key="index">
              <slot :item="item">
                  {{item.name}}
              </slot>
          </li>
      </ul>
  </div>
</template>

<script>
export default {
  name: '',
  props:['stars']
}
</script>

<style scoped>

</style>
