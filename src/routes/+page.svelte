<script>
	import { v4 as uuid } from 'uuid';

	import Header from '../components/Header.svelte';
	import List from '../components/List.svelte';
	import Info from '../components/Info.svelte';

	let newItem = '';
	let editItem = '';

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
	$: total = fetchTodos.length;

	const handleCHKBox = (id) => {
		todos = todos.map((todo) => {
			if (todo.id === id) todo.done = !todo.done;
			return todo;
		});
	};

	const addNewItem = (e) => {
		if (!newItem) return;

		if (e.keyCode === 13) {
			const newListItem = {
				id: uuid(),
				content: newItem,
				done: false
			};
			todos = [...todos, newListItem];
			newItem = '';
		}
	};

	const handleEditItem = (id) => {
		editItem = id;
	};

	const updateItem = (e, item) => {
		if (e.keyCode === 13) {
			todos = todos.map((todo) => {
				if (todo.id === item.id) {
					todo = item;
				}
				editItem = '';
				return todo;
			});
		}
	};

	const deleteItem = (id) => {
		todos = todos.filter((todo) => todo.id !== id);
	};
</script>

<!-- 'bind:newItem' 확인하기 -->
<Header bind:newItem {addNewItem} />
<Info {total} />
<List {fetchTodos} {handleCHKBox} {editItem} {handleEditItem} {updateItem} {deleteItem} />
