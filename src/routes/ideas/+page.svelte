<script lang="ts">
	import Dashboard from '$lib/components/idea/dashboard.svelte';

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

<Dashboard {ideas} onNewIdea={() => console.log('New idea!')} />
