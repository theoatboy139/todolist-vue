<template>
  <div id="app">
    <TodoList/>
  </div>
</template>


<script>
import TodoList from './components/TodoList.vue'
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  components: {
    TodoList
  }
}
</script>

<style>
</style>
