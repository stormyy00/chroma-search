<script lang="ts">
	import { MapPin, Briefcase, ChevronDown } from 'lucide-svelte';
	import * as Card from '$lib/components/ui/card/index.js';
	import * as Collapsible from '$lib/components/ui/collapsible/index.js';
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { Button } from './ui/button/index.js';

	let { job } = $props();
	let open = $state(false);
</script>

<Card.Root class="group bg-grey-900 transition-all hover:border-cyan-400">
	<Card.Content class=" mx-4">
		<Collapsible.Root bind:open>
			<div class="flex items-center gap-4">
				<div class="shrink-0">
					<img
						src={job.logo || '/placeholder.svg'}
						alt={`${job.company} logo`}
						class="size-10 rounded border border-border bg-secondary object-cover"
					/>
				</div>

				<div class="grid flex-1 grid-cols-1 gap-2 md:grid-cols-[2fr_1fr_1fr_auto] md:items-center">
					<div class="min-w-0">
						<a
							href={job.link}
							class="text-base font-semibold text-cyan-400 hover:text-cyan-300 hover:underline"
						>
							{job.title}
						</a>
						<p class="text-sm text-white">{job.company}</p>
					</div>

					<div class="flex flex-wrap items-center gap-3 text-sm text-white/70">
						<div class="flex items-center gap-1">
							<MapPin class="size-3.5" />
							<span>{job.location}</span>
						</div>
						<div class="flex items-center gap-1">
							<Briefcase class="size-3.5" />
							<span>{job.type}</span>
						</div>
					</div>

					<div class="flex flex-col gap-1">
						<p class="text-sm font-semibold text-white">{job.salary}</p>
						<p class="text-xs text-white/70">{job.posted}</p>
					</div>

					<Collapsible.Trigger class="ml-auto rounded-full transition-opacity hover:opacity-80">
						<Button
							size="sm"
							class="h-8 w-8 cursor-pointer bg-transparent p-0 text-white hover:bg-gray-700"
						>
							<ChevronDown
								class="size-4 transition-transform duration-200  {open ? 'rotate-180' : ''}"
							/>
						</Button>
					</Collapsible.Trigger>
				</div>
			</div>

			<Collapsible.Content class="mt-3 border-t border-border pt-3">
				<div class="space-y-3">
					<p class="text-sm text-white/90">
						{job.description}
					</p>

					<div class="flex flex-wrap gap-2">
						{#each job.tags as tag}
							<Badge
								variant="secondary"
								class="bg-gradient-to-r from-cyan-400/80 to-blue-500/80 text-xs text-white "
								>{tag}</Badge
							>
						{/each}
					</div>
				</div>
			</Collapsible.Content>
		</Collapsible.Root>
	</Card.Content>
</Card.Root>
