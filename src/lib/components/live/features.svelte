<script lang="ts">
	import { BookOpen, Star, Share2 } from '@lucide/svelte';

	let hoveredFeature: number | null = null;

	const features = [
		{
			icon: BookOpen,
			title: 'Capture Ideas',
			description: 'Write down your thoughts as they bloom. No friction, just creation.'
		},
		{
			icon: Star,
			title: 'Rate & Organize',
			description: 'Give each idea its moment. Rate and prioritize what matters most.'
		},
		{
			icon: Share2,
			title: 'Share & Collaborate',
			description:
				'Send ideas to friends or reviewers with a simple link. Get feedback that helps you grow.'
		}
	];
</script>

<div class="relative z-10 mx-auto max-w-7xl px-6 pb-32">
	<div class="mb-16 text-center">
		<h2 class="mb-4 text-4xl font-bold text-bb-ink">
			Everything You Need to <span class="text-bb-blue">Bloom</span>
		</h2>
		<p class="mx-auto max-w-2xl text-lg text-bb-ink/70">
			Simple, powerful tools to help your ideas grow from seed to harvest
		</p>
	</div>

	<div class="grid gap-8 md:grid-cols-3">
		{#each features as feature, idx}
			<div
				class="group relative cursor-pointer rounded-2xl border border-white/50 bg-bb-paper/70 p-8 shadow-lg backdrop-blur-sm transition-all hover:-translate-y-2 hover:shadow-xl"
				on:mouseenter={() => (hoveredFeature = idx)}
				on:mouseleave={() => (hoveredFeature = null)}
				role="button"
				tabindex="0"
			>
				<div
					class="mb-6 flex h-14 w-14 items-center justify-center rounded-2xl bg-gradient-to-br from-bb-blue to-bb-moss transition-transform {hoveredFeature ===
					idx
						? 'scale-110 rotate-6'
						: ''}"
				>
					<svelte:component this={feature.icon} class="h-6 w-6 text-white" />
				</div>
				<h3 class="mb-3 text-xl font-bold text-bb-ink">
					{feature.title}
				</h3>
				<p class="leading-relaxed text-bb-ink/70">
					{feature.description}
				</p>
			</div>
		{/each}
	</div>
</div>
