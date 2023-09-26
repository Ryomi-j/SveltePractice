<script>
    export let todoValue
    export let handleAddItem
</script>

<header>
	<h1>Svelte ToDo</h1>
	<input type="text" bind:value={todoValue} on:keyup={handleAddItem}/>
</header>

<style>
	header {
        text-align: center;
        background: green
	}
    input {
        width: 80%;
    }
</style>
