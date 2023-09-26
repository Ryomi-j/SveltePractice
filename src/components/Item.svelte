<script>
	export let todo;
	export let handleCheckTodo;
	export let editMode;
	export let handleEditMode;
	export let deleteTodoItem;
    export let handleEditItem
</script>

<li class="wrapper">
	<div class="item">
		<input type="checkbox" bind:checked={todo.done} on:click={() => handleCheckTodo(todo.id)} />
		<!-- svelte-ignore a11y-no-static-element-interactions -->
		{#if editMode === todo.id}
			<input type="text" bind:value={todo.content} on:focusout={() => handleEditItem(todo)} />
		{:else}
			<div class="content" on:dblclick={() => handleEditMode(todo.id)}>{todo.content}</div>
		{/if}
	</div>
	<button on:click={() => deleteTodoItem(todo.id)}>X</button>
</li>

<style>
	.wrapper {
		display: flex;
		justify-content: space-between;
	}

    .item {
        display: flex;
        align-items: center;
        height: 2rem;
    }
</style>
