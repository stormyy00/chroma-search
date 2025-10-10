<script lang="ts">
	import { Sparkles, ArrowRight, Star } from '@lucide/svelte';
</script>

<div class="relative z-10 mx-auto max-w-7xl px-6 pt-20 pb-32">
	<div class="mx-auto max-w-4xl text-center">
		<div
			class="mb-6 inline-block rounded-full border border-bb-blue/20 bg-bb-paper/80 px-4 py-2 shadow-sm backdrop-blur-sm"
		>
			<span class="flex items-center gap-2 text-sm font-medium text-bb-blue-dark">
				<Sparkles class="h-4 w-4" />
				Where Ideas Take Root
			</span>
		</div>

		<h1 class="mb-6 text-6xl leading-tight font-bold md:text-7xl">
			<span
				class="bg-gradient-to-r from-bb-ink via-bb-blue-dark to-bb-moss bg-clip-text text-transparent"
			>
				Your Garden of
			</span>
			<br />
			<span class="bg-gradient-to-r from-bb-blue to-bb-moss bg-clip-text text-transparent">
				Infinite Ideas
			</span>
		</h1>

		<p class="mx-auto mb-12 max-w-2xl text-xl leading-relaxed text-bb-ink/80">
			Capture every spark of inspiration. Watch your thoughts bloom into something beautiful. Share
			your ideas with the world, one note at a time.
		</p>

		<div class="mb-16 flex flex-wrap justify-center gap-4">
			<a
				href="/ideas"
				class="group hover:scale flex items-center gap-2 rounded-full bg-gradient-to-r from-bb-blue to-bb-moss px-8 py-4 text-lg font-medium text-white transition-all hover:shadow-xl"
			>
				Start BrainBlooming
				<ArrowRight class="h-5 w-5 transition-transform group-hover:translate-x-1" />
			</a>
			<!-- <button class="px-8 py-4 bg-bb-paper/90 backdrop-blur-sm text-bb-ink rounded-full hover:shadow-lg transition-all border border-bb-blue/20 text-lg font-medium">
          See How It Works
        </button> -->
		</div>

		<div class="relative mx-auto max-w-4xl">
			<div
				class="absolute inset-0 rounded-3xl bg-gradient-to-r from-bb-blue to-bb-moss opacity-20 blur-3xl"
			></div>
			<div
				class="relative rounded-3xl border border-white/50 bg-bb-paper/85 p-8 shadow-2xl backdrop-blur-xl"
			>
				<div class="mb-6 flex items-center gap-3 border-b border-bb-blue/20 pb-4">
					<div class="h-8 w-8 rounded-lg bg-gradient-to-br from-bb-blue to-bb-moss"></div>
					<div class="flex-1 text-left">
						<div class="text-sm font-medium text-bb-ink">Quick Idea</div>
						<div class="text-xs text-bb-ink/60">Just now</div>
					</div>
					<div class="flex gap-1">
						{#each [1, 2, 3, 4, 5] as star}
							<Star class="h-4 w-4 fill-bb-gold text-bb-gold" />
						{/each}
					</div>
				</div>
				<div class="space-y-3 text-left">
					<div class="h-3 w-3/4 animate-pulse rounded-full bg-bb-blue/20"></div>
					<div class="h-3 w-full animate-pulse rounded-full bg-bb-blue/20"></div>
					<div class="h-3 w-5/6 animate-pulse rounded-full bg-bb-blue/20"></div>
				</div>
			</div>
		</div>
	</div>
</div>
