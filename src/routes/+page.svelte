<script lang="ts">
	import * as Accordion from '$lib/components/ui/accordion/index.js';
	import PulsButton from '$lib/components/Animation/PulsButton.svelte';
	import { blur, fly, slide } from 'svelte/transition';
	import SparklesText from '$lib/components/Animation/SparklesText.svelte';
	import * as Dialog from '$lib/components/ui/dialog/index.js';
	let open = $state(false);
	let renderd = $state(false);
	function handleClick() {
		renderd = !renderd;
	}

	$effect(() => {
		if (renderd) {
			const timerOpen = setTimeout(() => {
				open = true;
			}, 2000);

			const timer = setTimeout(() => {
				open = false;
			}, 7000);

			return () => {
				clearTimeout(timer);
				clearTimeout(timerOpen);
			};
		}
	});
</script>

{#snippet code()}
	<pre>
<span class="bracket">&lt;</span><span class="tag">details</span><span class="bracket">&gt;</span>
    <span class="bracket">&lt;</span><span class="tag">summary</span><span class="bracket"
			>&gt;</span
		>
        <span class="bracket">&lt;</span><span class="tag">span</span><span class="bracket"
			>&gt;</span
		>	
		<span class="text">Personal Info</span><span class="bracket">&lt;/</span><span class="tag"
			>span</span
		><span class="bracket">&gt;</span>
    <span class="bracket">&lt;/</span><span class="tag">summary</span><span class="bracket"
			>&gt;</span
		>
    <span class="bracket">&lt;</span> <span class="tag">div</span><span class="bracket">&gt;</span>
        <span class="bracket">&lt;</span><span class="tag">p</span><span class="bracket">&gt;</span
		><span class="text"
			>Hello! I'm Ahmad Alajami, a dedicated and passionate front-end developer.</span
		><span class="bracket">&lt;/</span><span class="tag">p</span><span class="bracket">&gt;</span>
    <span class="bracket">&lt;/</span><span class="tag">div</span><span class="bracket">&gt;</span>
<span class="bracket">&lt;/</span><span class="tag">details</span><span class="bracket">&gt;</span>

<span class="bracket">&lt;</span><span class="tag">details</span><span class="bracket">&gt;</span>
    <span class="bracket">&lt;</span><span class="tag">summary</span><span class="bracket"
			>&gt;</span
		>
        <span class="bracket">&lt;</span><span class="tag">span</span><span class="bracket"
			>&gt;</span
		><span class="text">Skills</span><span class="bracket">&lt;/</span><span class="tag">span</span
		><span class="bracket">&gt;</span>
    <span class="bracket">&lt;/</span><span class="tag">summary</span><span class="bracket"
			>&gt;</span
		>
    <span class="bracket">&lt;</span><span class="tag">div</span><span class="bracket">&gt;</span>
        <span class="bracket">&lt;</span><span class="tag">p</span><span class="bracket">&gt;</span
		><span class="text">I specialize in modern JavaScript frameworks, including:</span><span
			class="bracket">&lt;/</span
		><span class="tag">p</span><span class="bracket">&gt;</span>
        <span class="bracket">&lt;</span><span class="tag">ul</span> <span class="attr-name"
			>class</span
		>=<span class="attr-value">"space-y-3"</span><span class="bracket">&gt;</span>
            <span class="bracket">&lt;</span><span class="tag">li</span><span class="bracket"
			>&gt;</span
		><span class="text">SvelteKit</span><span class="bracket">&lt;/</span><span class="tag">li</span
		><span class="bracket">&gt;</span>
            <span class="bracket">&lt;</span><span class="tag">li</span><span class="bracket"
			>&gt;</span
		><span class="text">Vue.js</span><span class="bracket">&lt;/</span><span class="tag">li</span
		><span class="bracket">&gt;</span>
            <span class="bracket">&lt;</span><span class="tag">li</span><span class="bracket"
			>&gt;</span
		><span class="text">React</span><span class="bracket">&lt;/</span><span class="tag">li</span
		><span class="bracket">&gt;</span>
            <span class="bracket">&lt;</span><span class="tag">li</span><span class="bracket"
			>&gt;</span
		><span class="text">Nuxt.js</span><span class="bracket">&lt;/</span><span class="tag">li</span
		><span class="bracket">&gt;</span>
            <span class="bracket">&lt;</span><span class="tag">li</span><span class="bracket"
			>&gt;</span
		><span class="text">Next.js</span><span class="bracket">&lt;/</span><span class="tag">li</span
		><span class="bracket">&gt;</span>
        <span class="bracket">&lt;/</span><span class="tag">ul</span><span class="bracket"
			>&gt;</span
		>
    <span class="bracket">&lt;/</span><span class="tag">div</span><span class="bracket">&gt;</span>
<span class="bracket">&lt;/</span><span class="tag">details</span><span class="bracket">&gt;</span>

<span class="bracket">&lt;</span><span class="tag">details</span><span class="bracket">&gt;</span>
    <span class="bracket">&lt;</span><span class="tag">summary</span><span class="bracket"
			>&gt;</span
		>
        <span class="bracket">&lt;</span><span class="tag">span</span><span class="bracket"
			>&gt;</span
		><span class="text">Projects</span><span class="bracket">&lt;/</span><span class="tag"
			>span</span
		><span class="bracket">&gt;</span>
    <span class="bracket">&lt;/</span><span class="tag">summary</span><span class="bracket"
			>&gt;</span
		>
    <span class="bracket">&lt;</span><span class="tag">div</span><span class="bracket">&gt;</span>
        <span class="bracket">&lt;</span><span class="tag">p</span><span class="bracket">&gt;</span
		><span class="text">Here are some of my recent projects:</span><span class="bracket">&lt;/</span
		><span class="tag">p</span><span class="bracket">&gt;</span>
        <span class="bracket">&lt;</span><span class="tag">ul</span> <span class="attr-name"
			>class</span
		>=<span class="attr-value">"space-y-10"</span><span class="bracket">&gt;</span>
            <span class="bracket">&lt;</span><span class="tag">li</span> <span class="attr-name"
			>class</span
		>=<span class="attr-value">"rounded-lg border-2 border-gray-700 p-4"</span><span class="bracket"
			>&gt;</span
		>
                <span class="bracket">&lt;</span><span class="tag">a</span> <span class="attr-name"
			>class</span
		>=<span class="attr-value">"underline"</span> <span class="attr-name">href</span>=<span
			class="attr-value">"https://grresin.com/"</span
		> <span class="attr-name">target</span>=<span class="attr-value">"_blank"</span><span
			class="bracket">&gt;</span
		><span class="text"> grresin.com </span><span class="bracket">&lt;/</span><span class="tag"
			>a</span
		><span class="bracket">&gt;</span>
                <span class="bracket">&lt;</span><span class="tag">p</span><span class="bracket"
			>&gt;</span
		><span class="text">A website built with SvelteKit and Pocketbase.</span><span class="bracket"
			>&lt;/</span
		><span class="tag">p</span><span class="bracket">&gt;</span>
            <span class="bracket">&lt;/</span><span class="tag">li</span><span class="bracket"
			>&gt;</span
		>
            <span class="bracket">&lt;</span><span class="tag">li</span> <span class="attr-name"
			>class</span
		>=<span class="attr-value">"rounded-lg border-2 border-gray-700 p-4"</span><span class="bracket"
			>&gt;</span
		>
                <span class="bracket">&lt;</span><span class="tag">a</span> <span class="attr-name"
			>class</span
		>=<span class="attr-value">"underline"</span> <span class="attr-name">href</span>=<span
			class="attr-value">"https://88logistics.vercel.app/"</span
		> <span class="attr-name">target</span>=<span class="attr-value">"_blank"</span><span
			class="bracket">&gt;</span
		>
                    <span class="text">88logistics.vercel.app</span>
                <span class="bracket">&lt;/</span><span class="tag">a</span><span class="bracket"
			>&gt;</span
		>
                <span class="bracket">&lt;</span><span class="tag">p</span><span class="bracket"
			>&gt;</span
		><span class="text">A logistics company website.</span><span class="bracket">&lt;/</span><span
			class="tag">p</span
		><span class="bracket">&gt;</span>
            <span class="bracket">&lt;/</span><span class="tag">li</span><span class="bracket"
			>&gt;</span
		>
            <span class="bracket">&lt;</span><span class="tag">li</span> <span class="attr-name"
			>class</span
		>=<span class="attr-value">"rounded-lg border-2 border-gray-700 p-4"</span><span class="bracket"
			>&gt;</span
		>
                <span class="bracket">&lt;</span><span class="tag">a</span> <span class="attr-name"
			>class</span
		>=<span class="attr-value">"underline"</span> <span class="attr-name">href</span>=<span
			class="attr-value">"https://atse-medica.vercel.app/"</span
		> <span class="attr-name">target</span>=<span class="attr-value">"_blank"</span><span
			class="bracket">&gt;</span
		>
                    <span class="text">atse-medica.vercel.app</span>
                <span class="bracket">&lt;/</span><span class="tag">a</span><span class="bracket"
			>&gt;</span
		>
                <span class="bracket">&lt;</span><span class="tag">p</span><span class="bracket"
			>&gt;</span
		><span class="text">A medical services website.</span><span class="bracket">&lt;/</span><span
			class="tag">p</span
		><span class="bracket">&gt;</span>
            <span class="bracket">&lt;/</span><span class="tag">li</span><span class="bracket"
			>&gt;</span
		>
        <span class="bracket">&lt;/</span><span class="tag">ul</span><span class="bracket"
			>&gt;</span
		>
    <span class="bracket">&lt;/</span><span class="tag">div</span><span class="bracket">&gt;</span>
<span class="bracket">&lt;/</span><span class="tag">details</span><span class="bracket">&gt;</span>

<span class="bracket">&lt;</span><span class="tag">details</span><span class="bracket">&gt;</span>
    <span class="bracket">&lt;</span><span class="tag">summary</span><span class="bracket"
			>&gt;</span
		>
        <span class="bracket">&lt;</span><span class="tag">span</span><span class="bracket"
			>&gt;</span
		><span class="text">Contact</span><span class="bracket">&lt;/</span><span class="tag">span</span
		><span class="bracket">&gt;</span>
    <span class="bracket">&lt;/</span><span class="tag">summary</span><span class="bracket"
			>&gt;</span
		>
    <span class="bracket">&lt;</span><span class="tag">div</span><span class="bracket">&gt;</span>
        <span class="bracket">&lt;</span><span class="tag">p</span><span class="bracket">&gt;</span
		><span class="text">You can reach me at:</span><span class="bracket">&lt;/</span><span
			class="tag">p</span
		><span class="bracket">&gt;</span>
        <span class="bracket">&lt;</span><span class="tag">ul</span><span class="bracket">&gt;</span
		>
            <span class="bracket">&lt;</span><span class="tag">li</span><span class="bracket"
			>&gt;</span
		>
                <span class="bracket">&lt;</span><span class="tag">strong</span><span
			class="bracket">&gt;</span
		><span class="text">Email:</span><span class="bracket">&lt;/</span><span class="tag"
			>strong</span
		><span class="bracket">&gt;</span>
                <span class="bracket">&lt;</span><span class="tag">a</span> <span class="attr-name"
			>href</span
		>=<span class="attr-value">"mailto:a.alajamai963@gmail.com"</span><span class="bracket"
			>&gt;</span
		><span class="text">a.alajamai963@gmail.com</span><span class="bracket">&lt;/</span><span
			class="tag">a</span
		><span class="bracket">&gt;</span>
            <span class="bracket">&lt;/</span><span class="tag">li</span><span class="bracket"
			>&gt;</span
		>
            <span class="bracket">&lt;</span><span class="tag">li</span><span class="bracket"
			>&gt;</span
		>
                <span class="bracket">&lt;</span><span class="tag">strong</span><span
			class="bracket">&gt;</span
		><span class="text">Phone:</span><span class="bracket">&lt;/</span><span class="tag"
			>strong</span
		><span class="bracket">&gt;</span>
                <span class="bracket">&lt;</span><span class="tag">a</span> <span class="attr-name"
			>href</span
		>=<span class="attr-value">"tel:+963963931267"</span><span class="bracket">&gt;</span><span
			class="text">+963 963 931 267</span
		><span class="bracket">&lt;/</span><span class="tag">a</span><span class="bracket">&gt;</span>
            <span class="bracket">&lt;/</span><span class="tag">li</span><span class="bracket"
			>&gt;</span
		>
        <span class="bracket">&lt;/</span><span class="tag">ul</span><span class="bracket"
			>&gt;</span
		>
    <span class="bracket">&lt;/</span><span class="tag">div</span><span class="bracket">&gt;</span>
<span class="bracket">&lt;/</span><span class="tag">details</span><span class="bracket">&gt;</span>
</pre>
{/snippet}
<Dialog.Root {open}>
	<Dialog.Content>
		<Dialog.Header>
			<Dialog.Title>A Small Demonstration ✨</Dialog.Title>
			<Dialog.Description>
				This is just a small example of what I can build. If you need a custom solution for your
				project, let's connect. I'm ready to bring your ideas to life. 🚀
			</Dialog.Description>
		</Dialog.Header>
	</Dialog.Content>
</Dialog.Root>
<div class="my-10 flex justify-between">
	<div><h1>{!renderd ? 'Ahmad Alajami Portfolio' : ''}</h1></div>
	<div>
		<PulsButton onclick={handleClick}>Let's {!renderd ? 'Render' : 'unRender'} this 🪄</PulsButton>
	</div>
</div>
{#if !renderd}
	<section
		class={['conatainer mx-auto', renderd ? 'overflow-hidden' : '']}
		out:blur={{ amount: 10, duration: 300, opacity: 0 }}
		in:fly={{ y: 100, duration: 300, delay: 500 }}
	>
		{@render code()}
	</section>
{/if}

{#if renderd}
	<section in:blur={{ amount: 10, duration: 600, opacity: 1 }}>
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
							<a class="underline" href="mailto:a.alajamai963@gmail.com">a.alajamai963@gmail.com</a>
						</li>
						<li>
							<strong>Phone:</strong>
							<a class="underline" href="tel:+963963931267">+963 963 931 267</a>
						</li>
					</ul>
				</Accordion.Content>
			</Accordion.Item>
		</Accordion.Root>
	</section>
{/if}

<style>
	pre {
		margin: 0;
		white-space: pre-wrap;
		word-wrap: break-word;
	}

	.tag {
		color: #4ec9b0;
	}
	.attr-name {
		color: #9cdcfe;
	}
	.attr-value {
		color: #ce9178;
	}
	.text {
		color: #d4d4d4;
	}
	.bracket {
		color: #808080;
	}
</style>
