<script>
	export let todo;
	export let handleCHKBox;
	export let handleEditItem;
	export let editItem;
	export let updateItem
	export let deleteItem
</script>

<div class="wrapper">
	<div class="item">
		<input type="checkbox" bind:checked={todo.done} on:click={() => handleCHKBox(todo.id)} />
		<!-- svelte-ignore a11y-click-events-have-key-events -->
		<!-- svelte-ignore a11y-no-static-element-interactions -->

		{#if todo.id === editItem}
			<input type="text" bind:value={todo.content} on:keyup={(e) => updateItem(e, todo)} />
		{:else}
			<div class="content" on:click={() => handleEditItem(todo.id)}>{todo.content}</div>
		{/if}
	</div>
	<button on:click={() => deleteItem(todo.id)}>X</button>
</div>

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
