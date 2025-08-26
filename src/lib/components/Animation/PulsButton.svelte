<script lang="ts">
	import { cn } from '$lib/utils';

	interface Props {
		pulseColor?: string;
		duration?: string;
		class?: string;
		onclick?: () => void;
		children?: import('svelte').Snippet;
	}

	let {
		pulseColor = 'var(--secondary)',
		duration = '1.5s',
		class: className = '',
		onclick,
		children
	}: Props = $props();
</script>

<button
	class={cn(
		'relative flex cursor-pointer items-center justify-center rounded-lg bg-primary px-4 py-2 text-center text-black',
		className
	)}
	style:--pulse-color={pulseColor}
	style:--duration={duration}
	{onclick}
>
	<div class="relative z-10">
		{#if children}{@render children()}{:else}Button{/if}
	</div>
	<div
		class="absolute top-1/2 left-1/2 size-full -translate-x-1/2 -translate-y-1/2 animate-pulse rounded-lg bg-inherit"
	></div>
</button>
