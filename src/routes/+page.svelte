<script>
	import { v4 as uuid } from 'uuid';

	import Header from '../components/Header.svelte';
	import List from '../components/List.svelte';

	let newValue = '';

	let editMode = '';

	let todos = [
		{
			id: uuid(),
			content: '첫 번째 할 일',
			done: false
		},
		{
			id: uuid(),
			content: '두 번째 할 일',
			done: false
		},
		{
			id: uuid(),
			content: '세 번째 할 일',
			done: false
		},
		{
			id: uuid(),
			content: '네 번째 할 일',
			done: false
		}
	];

	$: fetchTodos = todos;

	const handleCheckTodo = (id) => {
		fetchTodos.map((todo) => {
			if (todo.id === id) todo.done = !todo.done;

			return todo;
		});
	};

	const handleAddItem = (e) => {
		if (e.keyCode === 13) addTodoItem();
	};

	const addTodoItem = () => {
		if (newValue) {
			const newItem = {
				id: uuid(),
				content: newValue,
				done: false
			};

			todos = [...todos, newItem];
			newValue = '';
		}
	};

	const handleEditMode = (id) => {
		editMode = id;
	};

	const handleEditItem = (todoItem) => {
		todos = todos.map((todo) => {
			if (todo.id === todoItem.id) {
				todo = todoItem;
			}
			return todo;
		});

		editMode = '';
	};

	const deleteTodoItem = (id) => {
		todos = todos.filter((todo) => todo.id !== id);
	};
</script>

<Header bind:newValue {handleAddItem} />
<List {todos} {handleCheckTodo} {editMode} {handleEditMode} {handleEditItem} {deleteTodoItem} />
