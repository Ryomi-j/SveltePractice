<script>
	import Item from './Item.svelte';

	export let todos;
	export let handleTodoCHK;
	export let editItem;
	export let handleEditMode;
	export let updateItem;
	export let deleteItem;
</script>

	<ul>
		{#each todos as todo}
			<Item {todo} {handleTodoCHK} {editItem} {handleEditMode} {updateItem} {deleteItem} />
		{/each}
	</ul>



