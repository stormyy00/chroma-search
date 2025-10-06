<script lang="ts">
	import { Button } from './ui/button/index.js';
</script>

<div class="fixed top-0 right-0 left-0 z-50 bg-gray-900 py-5 shadow-lg transition-all duration-300">
	<div class="container mx-auto flex items-center justify-between px-6">
		<div class="flex items-center gap-2 drop-shadow-lg">
			<span
				class="text-2xl font-extrabold tracking-wide text-white drop-shadow-[0_0_10px_rgba(34,211,238,0.5)]"
			>
				Chroma
				<span class="bg-gradient-to-r from-cyan-400 to-blue-500 bg-clip-text text-transparent">
					10
				</span>
			</span>
		</div>

		<div class="flex items-center gap-x-4">
			<a
				href="/dashboard"
				class="font-semibold text-white transition-all duration-200 hover:text-cyan-400 hover:underline"
			>
				Dashboard
			</a>
			<Button
				class="rounded-2xl bg-gradient-to-r from-cyan-400 to-blue-500 font-semibold text-white shadow shadow-cyan-500/50 transition-all duration-300 hover:scale-105"
			>
				Try Now
			</Button>
			<Button
				class="rounded-2xl bg-gradient-to-r from-cyan-400 to-blue-500 font-semibold text-white shadow shadow-cyan-500/50 transition-all duration-300 hover:scale-105"
			>
				Profile
			</Button>
		</div>
	</div>
</div>
