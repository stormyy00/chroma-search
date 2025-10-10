<script lang="ts">
	import { Flower, Sparkles } from '@lucide/svelte';
</script>

<div class="relative z-10 mx-auto max-w-7xl px-6 pb-32">
	<div
		class="relative overflow-hidden rounded-3xl bg-gradient-to-r from-bb-blue to-bb-moss p-12 text-center md:p-16"
	>
		<div class="absolute inset-0 opacity-10">
			<div class="absolute top-10 left-10">
				<Flower class="h-32 w-32 animate-pulse text-white" />
			</div>
			<div class="absolute right-10 bottom-10">
				<Sparkles class="h-40 w-40 animate-pulse text-white" />
			</div>
		</div>

		<div class="relative z-10">
			<h2 class="mb-6 text-4xl font-bold text-white md:text-5xl">Ready to Let Your Ideas Bloom?</h2>
			<p class="mx-auto mb-8 max-w-2xl text-xl text-white/90">
				Join thousands of creative minds cultivating their thoughts in BrainBloom
			</p>
			<button
				class="rounded-full bg-bb-paper px-10 py-4 text-lg font-bold text-bb-blue-dark transition-all hover:scale-105 hover:shadow-2xl"
			>
				Start Growing Today
			</button>
		</div>
	</div>
</div>
