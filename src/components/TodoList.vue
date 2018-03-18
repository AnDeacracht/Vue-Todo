<template>
  <div>
    <p>Completed Tasks: {{ todos.filter(todo => todo.done === true).length }}</p>
    <p>Pending Tasks: {{ todos.filter(todo => todo.done === false).length }}</p>
    <todo v-for="(todo, index) in todos" v-bind:todo="todo" v-bind:key="index"></todo>
  </div>
</template>

<script type="text/javascript">

import Todo from './Todo'

export default {
  props: ['todos'],
  components: {
    Todo
  }
}

</script>

<style type="text/css"></style>
