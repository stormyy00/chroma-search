<script lang="ts">
	// import Dashboard from '$lib/components/idea/dashboard.svelte';

	let ideas = [
		{
			id: 1,
			title: 'Build a garden automation system',
			content: 'Create an IoT system...',
			rating: 4,
			createdAt: '2025-10-08',
			tags: ['tech', 'hobby'],
			isStarred: false
		}
	];
</script>

<!-- <Dashboard {ideas} onNewIdea={() => console.log('New idea!')} />\ -->
{#each ideas as idea (idea.id)}
	<div class="p-4">
		<p class="text-lg font-bold">{idea.title}</p>
		<p class="text-sm text-gray-600">{idea.content}</p>
		<p class="text-xs text-gray-500">Tags: {idea.tags.join(', ')}</p>
	</div>
{/each}
