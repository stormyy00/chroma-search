<!-- <script lang="ts">
	import Home from '../lib/components/home.svelte';

	export let data: {
		data: {
			link: string;
			title: string;
			snippet: string;
			source: string;
			indexed_at: string;
		}[];
	};

	console.log('page', data.data);
</script>

<main>
	<Home />
	<div class="p-4 text-black">
		{#each data.data as job}
			<div class="mb-4 w-fit rounded border border-gray-300 p-4">
				<a class="text-cyan-400" href={job.link}>{job.title}</a>
				<p>{job.snippet}</p>
				<p>{job.source}</p>
				<p>{job.indexed_at}</p>
			</div>
		{/each}
	</div>
</main> -->

<script>
	import Action from '$lib/components/live/action.svelte';
	import Features from '$lib/components/live/features.svelte';
	import Home from '$lib/components/live/home.svelte';
	import Footer from '$lib/components/live/footer.svelte';
	import { Sparkles, Cloud, Flower } from '@lucide/svelte';
</script>

<div
	class="relative min-h-screen overflow-hidden bg-gradient-to-br from-bb-bg via-bb-paper to-bb-tea"
>
	<div class="absolute top-20 left-10 animate-pulse opacity-10">
		<Cloud class="h-32 w-32 text-bb-blue" />
	</div>
	<div class="absolute top-40 right-20 animate-pulse opacity-10">
		<Flower class="h-24 w-24 text-bb-moss" />
	</div>
	<div class="absolute bottom-20 left-1/4 animate-pulse opacity-10">
		<Sparkles class="h-20 w-20 text-bb-gold" />
	</div>
	<Home />
	<Features />
	<Action />
	<Footer />
</div>
