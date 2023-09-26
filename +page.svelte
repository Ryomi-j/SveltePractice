<script>
    import {v4 as uuid} from 'uuid'

	import Header from './src/components/Header.svelte';
	import List from './src/components/List.svelte';

    let todoValue = ''

    let todos = [
        {
            id: uuid(),
            content: '첫 번째 할 일',
            done: false,
        },
        {
            id: uuid(),
            content: '두 번째 할 일',
            done: false,
        },
        {
            id: uuid(),
            content: '세 번째 할 일',
            done: false,
        },
        {
            id: uuid(),
            content: '네 번째 할 일',
            done: false,
        },
    ]

    $: fetchTodos = todos

    const handleCheckTodo = (id) => {
        fetchTodos.map(todo => {
            if(todo.id === id) todo.done = !todo.done
            return todo
        })
    }

    const handleTodoInputKeyUp = (e) => {
        if(e.keyCode === 13) addTodo()
    }

    const addTodo = () => {
        if(todoValue) {
            const newTodo = {
                id: uuid(),
                content: todoValue,
                done: false
            }

            todos = [...todos, newTodo]
            todoValue = ''
        }
    }
</script>

<!-- 상위요소의 state 값도 변경시키기 위해 bind를 사용한다 -->
<Header bind:todoValue={todoValue} {handleTodoInputKeyUp}/>
<List {fetchTodos} {handleCheckTodo}/>
