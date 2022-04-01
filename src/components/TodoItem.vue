<template>
<!--  click 触发子组件的handleItemClick， 执行的是delete-->
  <li @click="handleItemClick">{{content}}</li>
</template>

<script>
export default {
  name: 'TodoItem',
  props: ['content'],
  methods: {
    handleItemClick: function() {
      this.$emit('delete');
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
li {
  list-style: none;
  padding: 10px;
  border-bottom: 1px solid #ccc;
}
</style>
