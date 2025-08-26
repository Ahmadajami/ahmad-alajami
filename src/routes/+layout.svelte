<script lang="ts">
	import '../app.css';
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<title>Ahmad alajami - Front-End Developer</title>
</svelte:head>

<main class="container mx-auto overflow-hidden pt-12">
	{@render children?.()}
</main>
