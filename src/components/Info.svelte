<script>
    export let total
</script>

<div class="category">
    <div>Count: {total}</div>
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