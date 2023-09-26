 <script>
	export let todo;
	export let handleTodoCHK;
	export let editItem;
    export let handleEditMode
    export let updateItem
    export let deleteItem
</script>

<li class="wrapper">
	<div class="item">
		<input type="checkbox" bind:checked={todo.checked} on:click={() => handleTodoCHK(todo.id)} />
		{#if todo.id === editItem}
			<input type="text" bind:value={todo.content} on:focusout={() => updateItem(todo)}/>
		{:else}
			<!-- svelte-ignore a11y-no-static-element-interactions -->
			<!-- svelte-ignore a11y-click-events-have-key-events -->
			<div class="content" on:click={() => handleEditMode(todo)}>{todo.content}</div>
		{/if}
	</div>
	<button on:click={() => deleteItem(todo.id)}>X</button>
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
