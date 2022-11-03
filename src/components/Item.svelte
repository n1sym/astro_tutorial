<script>
	import { slide } from "svelte/transition";
	export let entry
	let isOpen = false
	const toggle = () => isOpen = !isOpen
</script>
<style>
	button {border: none; background: none; display:block; color: inherit; font-size: 16px; cursor: pointer; margin: 0; padding: 0}
</style>
<button on:click={toggle} aria-expanded={isOpen}> {entry[0]} </button>
{#if isOpen}
<ul transition:slide={{ duration: 300 }}>
	{#each entry[1] as item}
	<li>{item}</li>
	{/each}
</ul>
{/if}