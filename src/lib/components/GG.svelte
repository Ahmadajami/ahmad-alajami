<script>
	let sections = ['Section 1', 'Section 2', 'Section 3'];
</script>

{#each sections as section}
	<section class="snap-section">
		<h1>{section}</h1>
	</section>
{/each}

<style>
	.snap-section {
		height: 100vh;
		scroll-snap-align: start;
		display: flex;
		justify-content: center;
		align-items: center;
		font-size: 3rem;
	}

	.snap-section:nth-child(1) {
		background: #f87171;
	}
	.snap-section:nth-child(2) {
		background: #60a5fa;
	}
	.snap-section:nth-child(3) {
		background: #34d399;
	}
</style>
