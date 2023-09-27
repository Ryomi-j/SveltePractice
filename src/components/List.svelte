<script>
	import Item from './Item.svelte';
	
	export let fetchTodos;
	export let handleCHKBox;
	export let handleEditItem;
	export let editItem;
	export let updateItem;
	export let deleteItem;
</script>

<ul>
	{#each fetchTodos as todo}
		<Item {todo} {handleCHKBox} {editItem} {handleEditItem} {updateItem} {deleteItem}/>
	{/each}
</ul>
