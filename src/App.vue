<template>
  <div class="container">
    <column-list :list="list"></column-list>
  </div>
</template>

<script lang="ts">
import { computed, defineComponent, PropType } from 'vue'
import 'bootstrap/dist/css/bootstrap.min.css'
import ColumnList, { ColumnProps } from './components/ColumnList.vue'

const testData:ColumnProps[] = [
  {
    id: 1,
    title: 'test1的专栏',
    description: '我是 test1 专栏的简介，读我你可以快速了解文章全貌',
    avatar: 'https://www.jzy.world/m/computer.png'
  }, 
  {
    id: 2,
    title: 'test2的专栏',
    description: '我是 test2 专栏的简介，读我你可以快速了解文章全貌',
    avatar: 'https://www.jzy.world/m/computer.png'
  }, 
  {
    id: 3,
    title: 'test3的专栏',
    description: '我是 test3 专栏的简介，读我你可以快速了解文章全貌'
    //avatar: 'https://www.jzy.world/m/square.png'
  }, 
  {
    id: 4,
    title: 'test4的专栏',
    description: '我是 test4 专栏的简介，读我你可以快速了解文章全貌',
    avatar: 'https://www.jzy.world/m/computer.png'
  }
]

export default defineComponent({
  name: 'App',
  components: {
    ColumnList
  },
  setup() {
    return { list:testData }
  }
})
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
