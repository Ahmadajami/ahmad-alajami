<script lang="ts">
	import '../app.css';
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<title>Ahmad alajami - Front-End Developer</title>
</svelte:head>
<h1 class="text-center text-wrap">Ahmad alajami Portfolio</h1>

<main>
	{@render children?.()}
</main>
