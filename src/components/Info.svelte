<script>
    import Constant from "../constant";
    export let total
    export let handleViewMode
</script>

<div class="category">
    <div>Count: {total}</div>
    <div>
        <button on:click={() => handleViewMode(Constant.ALL)}>ALL</button>
        <button on:click={() => handleViewMode(Constant.ACTIVE)}>ACTIVE</button>
        <button on:click={() => handleViewMode(Constant.DONE)}>DONE</button>
    </div>
</div>

<style>
	.category {
		display: flex;
		justify-content: space-between;
	}
</style>