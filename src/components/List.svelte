<script>
	import Item from './Item.svelte';

	import { fade } from 'svelte/transition';
	import { flip } from 'svelte/animate';

	export let fetchTodos;
	export let handleCHKBox;
	export let handleEditItem;
	export let editItem;
	export let updateItem;
	export let deleteItem;
</script>

<ul>
	{#each fetchTodos as todo, idx(todo)}
	<!-- animate는 each block에서 key값과 함께 사용 가능 -->
		<li 
			in:fade 
			out:fade={{ duration: 100 }} 
			animate:flip={{ duration: 1000 }} 
		>
			<Item {todo} {handleCHKBox} {editItem} {handleEditItem} {updateItem} {deleteItem} />
		</li>
	{/each}
</ul>
