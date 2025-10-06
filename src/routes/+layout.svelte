<script lang="ts">
	import Navigation from '$lib/components/navigation.svelte';
	import '../app.css';

	let { children } = $props();
</script>

<Navigation />

{@render children()}
