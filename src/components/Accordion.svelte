<script>
	import Item from './Item.svelte'

  export let test;

	const data = {
		'続きを読む': [test],
	}
</script>
{#each Object.entries(data) as entry}
<Item {entry} />
{/each}