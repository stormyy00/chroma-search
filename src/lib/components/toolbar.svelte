<script lang="ts">
	import { Button } from '$lib/components/ui/button/index.js';

	let { selectedType = $bindable(), selectedLocation = $bindable() } = $props();

	const jobTypes = [
		{ value: 'all', label: 'All' },
		{ value: 'Full-time', label: 'Full-time' },
		{ value: 'Contract', label: 'Contract' },
		{ value: 'Part-time', label: 'Part-time' }
	];

	const locations = [
		{ value: 'all', label: 'All' },
		{ value: 'remote', label: 'Remote' },
		{ value: 'onsite', label: 'On-site' }
	];
</script>

<div class="flex flex-wrap items-center gap-4">
	<div class="flex items-center gap-2">
		<span class="text-sm font-medium text-white">Type:</span>
		<div class="flex items-center gap-1">
			{#each jobTypes as type}
				<Button
					size="sm"
					onclick={() => (selectedType = type.value)}
					class={`bg-gradient-to-r from-cyan-400 to-blue-500 text-white shadow ${selectedType === type.value ? 'opacity-100' : 'opacity-50 hover:bg-gray-700 hover:text-white'}`}
				>
					{type.label}
				</Button>
			{/each}
		</div>
	</div>

	<div class="flex items-center gap-2">
		<span class="text-sm font-medium text-white/70">Location:</span>
		<div class="flex items-center gap-1">
			{#each locations as location}
				<Button
					size="sm"
					onclick={() => (selectedLocation = location.value)}
					class={`bg-gradient-to-r from-cyan-400 to-blue-500 text-white shadow ${selectedLocation === location.value ? 'opacity-100' : 'opacity-50 hover:bg-gray-700 hover:text-white'}`}
				>
					{location.label}
				</Button>
			{/each}
		</div>
	</div>
</div>
