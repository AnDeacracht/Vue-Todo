<template>
  <div>
  	<div class="ui centered card" id="app-tasks">
    	<p class="ui header text">Completed Tasks: {{ todos.filter(todo => todo.done === true).length }}</p>
    	<p class="ui header text">Pending Tasks: {{ todos.filter(todo => todo.done === false).length }}</p>
    </div>
    <div>
    	<todo
    		v-for="(todo, index) in todos"
    		v-bind:todo="todo"
    		v-bind:key="index"
    		v-on:complete-todo="completeTodo(todo)"
    		></todo>
    </div>
  </div>
</template>

<script type="text/javascript">

import Todo from './Todo'

export default {
  props: ['todos'],
  components: {
    Todo
  },
  methods: {
  	completeTodo(childTodo) {
  		const todoIndex = this.todos.indexOf(childTodo)
  		this.todos[todoIndex].done = true
  	}
  }
}

</script>

<style type="text/css">

#app-tasks {
	margin-top: 20px;
	padding: 10px;
	text-align: center;
}

</style>
