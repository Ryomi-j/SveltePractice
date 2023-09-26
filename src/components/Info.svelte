<script>
    export let todoCount
</script>

<div class="category">
    <div>Count: {todoCount}</div>
    <div>
        <button>ALL</button>
        <button>ACTIVE</button>
        <button>DONE</button>
    </div>
</div>

<style>
	.category {
		display: flex;
		justify-content: space-between;
	}
</style>