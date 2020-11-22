<script>
	import { onMount } from 'svelte';
	export let name;
	let LoginForm;

	const sleep = ms => new Promise(f => setTimeout(f, ms));
	
	onMount(async () => {
		await sleep(1000); // simulate network delay
		LoginForm = (await import('./components/LoginForm.svelte')).default;
    });
</script>

<style lang="postcss">
	h1 {
		color: purple;
		@apply bg-gray-100;
	}
</style>

<template>
	<h1>Hello {name}!</h1>
	<svelte:component this={LoginForm} name="Click me"/>
</template>