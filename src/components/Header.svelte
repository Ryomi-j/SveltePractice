<script>
	export let newItem;
    export let addNewItem
</script>

<header>
	<h1>Svelte ToDo</h1>
	<input type="text" bind:value={newItem} on:keyup={addNewItem}/>
</header>

<style>
	header {
		text-align: center;
		background: green;
	}
	input {
		width: 80%;
	}
</style>
