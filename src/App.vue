<template>
  <input type="text" v-model="inputValue">
<!--  @click == v-on:click-->
  <button @click="handleBtn">提交</button>
  <ul>
<!--    v-bind 监控数据， content=item, 传递给子组件-->
    <todo-item :content="item" v-for="(item, index) in list" :key="index"  @delete="handleItemClick(index)"></todo-item>
<!--    @delete 监听子组件的delete 方法， 执行父组件的handleItemClick， 把父组件的content 改变， 子组件即变了-->
  </ul>
</template>

<script>
import TodoItem from "@/components/TodoItem"; // 注册组件
  export default {
    data () {
      return {
        inputValue: '',
        list: [
          'vue',
          'react',
        ]
      }
    },
    components: {
      TodoItem: TodoItem
    },
    methods: {
      handleBtn () {
        this.list.push(this.inputValue)
        this.inputValue = ''
      },
      handleItemClick (index) {
        this.list.splice(index, 1)
      }
    }
  }
</script>

<style>
  ul {
    list-style: none;
  }
</style>



