<script lang="ts">
	import Code from '$lib/components/Code.svelte';
	import Button from '$lib/components/ui/button/button.svelte';

	import * as Accordion from '$lib/components/ui/accordion/index.js';
	import { blur, fly } from 'svelte/transition';
	import SparklesText from '$lib/components/Animation/SparklesText.svelte';
	import Magicui from '$lib/components/Animation/Magic-card.svelte';
	import MagicCard from '$lib/components/Animation/Magic-card.svelte';
	import { goto } from '$app/navigation';

	let renderd = $state(false);
	function handleClick() {
		renderd = !renderd;
	}
</script>

<section class=" container mx-auto h-screen">
	<article class="flex h-full items-center justify-between">
		{#if !renderd}
			<div
				class="h-[80%] basis-[40%] overflow-scroll border border-accent-foreground"
				out:fly={{ x: 200, duration: 300 }}
			>
				<Code />
			</div>
			<div>
				<Button onclick={handleClick}>Let's Render this here</Button>
			</div>
		{/if}
		{#if renderd}
			<div class="w-full" in:blur={{ amount: 10, duration: 300, delay: 500, opacity: 1 }}>
				<div class="w-full text-center">
					<SparklesText text="Ahmad alajami Portfolio" />
				</div>
				<Accordion.Root type="single" class="w-full">
					<Accordion.Item value="personal-info">
						<!-- The Accordion.Trigger replaces the <summary> tag and handles the toggle state. -->
						<Accordion.Trigger>
							<span>Personal Info</span>
						</Accordion.Trigger>
						<!-- The Accordion.Content contains the collapsible content. -->
						<Accordion.Content>
							<p>Hello! I'm Ahmad Alajami, a dedicated and passionate front-end developer.</p>
						</Accordion.Content>
					</Accordion.Item>

					<Accordion.Item value="skills">
						<Accordion.Trigger>
							<span>Skills</span>
						</Accordion.Trigger>
						<Accordion.Content>
							<p>I specialize in modern JavaScript frameworks, including:</p>
							<ul class="space-y-3">
								<li>SvelteKit</li>
								<li>Vue.js</li>
								<li>React</li>
								<li>Nuxt.js</li>
								<li>Next.js</li>
							</ul>
						</Accordion.Content>
					</Accordion.Item>

					<Accordion.Item value="projects">
						<Accordion.Trigger>
							<span>Projects</span>
						</Accordion.Trigger>
						<Accordion.Content>
							<p>Here are some of my recent projects:</p>
							<ul class="space-y-3">
								<li>
									<a class="underline" href="https://grresin.com/" target="_blank"> grresin.com </a>
									<p>A website built with SvelteKit and Pocketbase.</p>
								</li>
								<li>
									<a class="underline" href="https://88logistics.vercel.app/" target="_blank">
										88logistics.vercel.app
									</a>
									<p>A logistics company website.</p>
								</li>
								<li>
									<a class="underline" href="https://atse-medica.vercel.app/" target="_blank">
										atse-medica.vercel.app
									</a>
									<p>A medical services website.</p>
								</li>
							</ul>
						</Accordion.Content>
					</Accordion.Item>

					<Accordion.Item value="contact">
						<Accordion.Trigger>Contact</Accordion.Trigger>
						<Accordion.Content>
							<p>You can reach me at:</p>
							<ul>
								<li>
									<strong>Email:</strong>
									<a class="underline" href="mailto:a.alajamai963@gmail.com"
										>a.alajamai963@gmail.com</a
									>
								</li>
								<li>
									<strong>Phone:</strong>
									<a class="underline" href="tel:+963963931267">+963 963 931 267</a>
								</li>
							</ul>
						</Accordion.Content>
					</Accordion.Item>
				</Accordion.Root>
			</div>
		{/if}
	</article>
</section>

<section class="h-screen">
	<h2><SparklesText text="My Experience" class="pt-12" /></h2>
	<article class="grid h-full grid-cols-2 gap-8 p-10">
		<MagicCard gradientColor="#fc03fc" class="flex h-full items-center justify-center text-center"
			><a
				class="h-full text-7xl font-medium text-wrap"
				target="_blank"
				href="https://newgrresin.vercel.app/"
			>
				Graffiti Resin
			</a></MagicCard
		>
		<MagicCard gradientColor="#FFD700" class="flex h-full items-center justify-center text-center"
			><a
				class="h-full text-7xl font-medium text-wrap"
				target="_blank"
				href="https://88logistics.vercel.app/"
			>
				88logistics
			</a></MagicCard
		>
		<MagicCard gradientColor="#03fcb6" class="flex h-full items-center justify-center text-center"
			><a
				class="h-full text-7xl font-medium text-wrap"
				target="_blank"
				href="https://atse-medica.vercel.app/"
			>
				Atse Medica
			</a></MagicCard
		>
	</article>
</section>

<style>
	section {
		scroll-snap-align: start;
	}
</style>
