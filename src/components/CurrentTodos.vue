<template>
	<div id="current-todos" class="container">
		<h3 v-if="todos.length > 0"> Current({{ todos.length }}) </h3>
		<ul class="list-group">
			<li class="list-group-item" v-for="todo in todos">
				{{ todo.body }}
				<div class="btn-group">
					<button type="button" class="btn btn-info btn-sm" @click="edit(todo)"> Edit </button>
					<button type="button" class="btn btn-success btn-sm" @click="complete(todo)"> Completed </button>
					<button type="button" class="btn btn-danger btn-sm" @click="remove(todo)"> Remove </button>
				</div>
			</li>
		</ul>
	</div>
</template>

<script>
export default {
	methods: {
		edit(todo) {
			this.$store.dispatch('editTodo', todo)
		},
		complete(todo) {
			this.$store.dispatch('completeTodo', todo)
		},
		remove(todo) {
			this.$store.dispatch('removeTodo', todo)
		}
	},
	computed: {
		todos() {
			return this.$store.getters.todos
		}
	}
}
</script>

<style>
	.btn-group {
		float: right;
	}
</style>