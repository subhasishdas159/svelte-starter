<script>
	export let params

	console.log(params)
</script>

{#if params}
	Movie {params.id}
{:else}
	Movie
{/if}