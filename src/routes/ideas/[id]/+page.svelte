<script lang="ts">
	// import { page } from '$app/stores';
	// import { ideasStore } from '$lib/stores/ideas.svelte';
	// import { Card, CardContent, CardHeader } from '$lib/components/ui/card/index.js';
	// import { Badge } from '$lib/components/ui/badge/index.js';
	// import { Button } from '$lib/components/ui/button/index.js';
	import { Lightbulb, Calendar, Star, ArrowLeft, ExternalLink } from '@lucide/svelte';
	// import type { Idea } from '$lib/types.js';

	// let idea = $state<Idea | null>(null);
	// let ideas = $state<Idea[]>([]);

	// ideasStore.ideas.subscribe((value) => {
	// 	ideas = value;
	// 	const id = $page.params.id;
	// 	idea = value.find((i) => i.id === id) || null;
	// });

	// function formatDate(dateString: string) {
	// 	const date = new Date(dateString);
	// 	return date.toLocaleDateString('en-US', {
	// 		month: 'long',
	// 		day: 'numeric',
	// 		year: 'numeric',
	// 		hour: '2-digit',
	// 		minute: '2-digit'
	// 	});
	// }

	// function copyLink() {
	// 	navigator.clipboard.writeText(window.location.href);
	// 	alert('Link copied to clipboard!');
	// }
</script>

<div class="my-20 min-h-screen bg-background">
	<div class="mx-auto max-w-3xl space-y-6 px-4 py-8">
		<!-- Header -->
		<header class="flex items-center justify-between">
			<a
				href="/"
				class="flex items-center gap-2 text-sm text-muted-foreground transition-colors hover:text-foreground"
			>
				<ArrowLeft class="h-4 w-4" />
				Back to Dashboard
			</a>
			<div class="flex items-center gap-2">
				<div
					class="flex h-8 w-8 items-center justify-center rounded-lg bg-primary text-primary-foreground"
				>
					<Lightbulb class="h-4 w-4" />
				</div>
				<span class="font-semibold">Idea Journal</span>
			</div>
		</header>

		<!-- {#if idea}
			<Card class="shadow-lg">
				<CardHeader class="space-y-4">
					<div class="space-y-2">
						<h1 class="text-3xl font-bold tracking-tight text-balance">{idea.title}</h1>
						<div class="flex items-center gap-2 text-sm text-muted-foreground">
							<Calendar class="h-4 w-4" />
							<span>{formatDate(idea.createdAt)}</span>
						</div>
					</div>

					{#if idea.tags.length > 0}
						<div class="flex flex-wrap gap-2">
							{#each idea.tags as tag}
								<Badge variant="secondary">{tag}</Badge>
							{/each}
						</div>
					{/if}

					{#if idea.rating > 0}
						<div class="flex items-center gap-2 border-t pt-2">
							<div class="flex items-center gap-1">
								{#each [1, 2, 3, 4, 5] as rating}
									<Star
										class="h-5 w-5 {rating <= idea.rating
											? 'fill-yellow-400 text-yellow-400'
											: 'text-muted-foreground/40'}"
									/>
								{/each}
							</div>
							<span class="text-sm font-medium">{idea.rating}/5</span>
						</div>
					{/if}
				</CardHeader>

				<CardContent class="space-y-6">
					{#if idea.description}
						<div class="prose prose-sm max-w-none">
							<p class="text-base leading-relaxed text-pretty whitespace-pre-wrap">
								{idea.description}
							</p>
						</div>
					{:else}
						<p class="text-muted-foreground italic">No description provided</p>
					{/if}

					<div class="border-t pt-4">
						<Button onclick={copyLink} class="w-full gap-2 sm:w-auto">
							<ExternalLink class="h-4 w-4" />
							Copy Share Link
						</Button>
					</div>
				</CardContent>
			</Card> -->

		<!-- Additional Context -->
		<!-- <Card class="bg-muted/50">
				<CardContent class="pt-6">
					<p class="text-center text-sm text-muted-foreground">
						This idea was shared from someone's Idea Journal. Create your own journal to capture and
						organize your ideas.
					</p>
				</CardContent>
			</Card>
		{:else}
			<Card class="shadow-lg">
				<CardContent class="py-12">
					<div class="space-y-3 text-center">
						<div class="flex justify-center">
							<div class="flex h-16 w-16 items-center justify-center rounded-full bg-muted">
								<Lightbulb class="h-8 w-8 text-muted-foreground" />
							</div>
						</div>
						<div>
							<h2 class="text-lg font-semibold">Idea not found</h2>
							<p class="text-sm text-muted-foreground">
								This idea may have been deleted or the link is incorrect.
							</p>
						</div>
						<div class="pt-4">
							<Button href="/" variant="outline">
								<ArrowLeft class="mr-2 h-4 w-4" />
								Go to Dashboard
							</Button>
						</div>
					</div>
				</CardContent>
			</Card>
		{/if} -->
	</div>
</div>
