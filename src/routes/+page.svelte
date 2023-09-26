<script>
	import { v4 as uuid } from 'uuid';

	import Header from '../components/Header.svelte';
	import List from '../components/List.svelte';
	import Info from '../components/Info.svelte';

    let todoValue = ''
    let editItem = ''

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
    $: todoCount = fetchTodos.length

	const handleTodoCHK = (id) => {
		fetchTodos.map((todo) => {
			if (todo.id === id) todo.done = !todo.done;

			return todo;
		});
	};

    const handleAddItem = (e) => {
        if(e.keyCode === 13) addItem()
    }

    const addItem = () => {
        if(todoValue){
            const newItem = {
                id: uuid(),
                content: todoValue,
                done: false
            }

            todos = [...todos, newItem]
            todoValue = ''
        }
    }

    const handleEditMode = (item) => {
        editItem = item.id
    }

    const updateItem = (item) => {
        todos = todos.map(todo => {
            if(todo.id === item.id) {
                todo = item
            }
            return todo
        })

        editItem = ''
    }

    const deleteItem = (id) => {
        todos = todos.filter(todo => todo.id !== id)
    }

</script>

<Header bind:todoValue {handleAddItem} />
<Info {todoCount}/>
<List {todos} {handleTodoCHK} {editItem} {handleEditMode} {updateItem} {deleteItem}/>
