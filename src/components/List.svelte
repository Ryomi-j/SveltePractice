<script>
	import Item from './Item.svelte';
	export let todos;
	export let handleCheckTodo;
	export let editMode;
	export let handleEditMode;
	export let handleEditItem;
	export let deleteTodoItem;
</script>

<main>
	<div class="category">
		<div>Count:</div>
		<div>
			<button>ALL</button>
			<button>ACTIVE</button>
			<button>DONE</button>
		</div>
	</div>
	<ul>
		{#each todos as todo}
			<Item
				{todo}
				{handleCheckTodo}
				{editMode}
				{handleEditMode}
				{handleEditItem}
				{deleteTodoItem}
			/>
		{/each}
	</ul>
</main>

<style>
	.category {
		display: flex;
		justify-content: space-between;
	}
</style>
