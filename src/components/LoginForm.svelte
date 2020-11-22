<script>
    import { onMount } from 'svelte';
    export let name;
	
	let Button;
	
	const sleep = ms => new Promise(f => setTimeout(f, ms));
	
	onMount(async () => {
		await sleep(1000); // simulate network delay
		Button = (await import('./Button.svelte')).default;
    });
    
</script>

<style lang="postcss">
    .container {
        @apply bg-red-100;
    }
</style>

<template>
    <div class="container">LoginForm:</div>
    <svelte:component this={Button} {name}/>
    <img src="./assets/svelte.png" alt="Svelte icon">
</template>