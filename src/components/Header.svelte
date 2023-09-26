<script>
    export let newValue
    export let handleAddItem
</script>

<header>
	<h1>Svelte ToDo</h1>
	<input type="text" bind:value={newValue} on:keyup={handleAddItem}/>
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
