<script>
	import Item from './Item.svelte';
	export let todos;
	export let handleCHKBox;
	export let handleEditItem;
	export let editItem;
	export let updateItem;
	export let deleteItem;
</script>

<ul>
	{#each todos as todo}
		<Item {todo} {handleCHKBox} {editItem} {handleEditItem} {updateItem} {deleteItem}/>
	{/each}
</ul>
