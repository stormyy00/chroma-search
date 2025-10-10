<script lang="ts">
	import { Sparkles } from '@lucide/svelte';
</script>

<footer class="relative z-10 border-t border-bb-blue/20 bg-bb-paper/50 backdrop-blur-sm">
	<div class="mx-auto max-w-7xl px-6 py-12">
		<div class="flex flex-col items-center justify-between gap-6 md:flex-row">
			<div class="flex items-center space-x-2">
				<div
					class="flex h-8 w-8 items-center justify-center rounded-full bg-gradient-to-br from-bb-blue to-bb-moss"
				>
					<Sparkles class="h-5 w-5 text-white" />
				</div>
				<span class="text-xl font-bold text-bb-ink">BrainBloom</span>
			</div>
			<div class="text-sm text-bb-ink/70">© 2025 BrainBloom. Where ideas grow.</div>
		</div>
	</div>
</footer>
