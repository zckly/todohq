<script>
	import TodoForm from '../../components/dashboard/TodoForm.svelte';
	import TodoList from '../../components/dashboard/TodoList.svelte';

	// State
	let todoInput = '';

	let todoList = [
		{
			text: 'Buy more milk',
			status: true
		},
		{
			text: 'Buy ramen',
			status: false
		}
	];

	function addToList() {
		todoList = [{ text: todoInput, status: true }, ...todoList];
	}
</script>

<div class="h-screen">
	<div class="flex min-h-full items-center justify-center py-12 px-4 sm:px-6 lg:px-8">
		<div class="w-full max-w-md space-y-16">
			<TodoForm {todoInput} add={addToList} />
			<TodoList todos={todoList} />
		</div>
	</div>
</div>
