<script lang="ts">
	import {
		Sparkles,
		PenLine,
		LayoutDashboard,
		Star,
		Share2,
		Settings,
		User,
		LogOut,
		Menu,
		X
	} from '@lucide/svelte';

	export let currentPage = 'dashboard';

	let mobileMenuOpen = false;
	let userMenuOpen = false;
	let signedIn = false;

	const navItems = [
		{ id: 'dashboard', label: 'Dashboard', icon: LayoutDashboard, href: '/ideas' },
		{ id: 'ideas', label: 'My Ideas', icon: PenLine, href: '/ideas' },
		{ id: 'starred', label: 'Starred', icon: Star, href: '/starred' },
		{ id: 'shared', label: 'Shared', icon: Share2, href: '/shared' }
	];

	const userMenuItems = [
		{ id: 'profile', label: 'Profile', icon: User },
		{ id: 'settings', label: 'Settings', icon: Settings },
		{ id: 'logout', label: 'Sign Out', icon: LogOut }
	];

	const toggleMobileMenu = () => {
		mobileMenuOpen = !mobileMenuOpen;
	};

	const toggleUserMenu = () => {
		userMenuOpen = !userMenuOpen;
	};

	const handleNavClick = (itemId: string) => {
		currentPage = itemId;
		mobileMenuOpen = false;
	};

	const handleUserMenuClick = (itemId: string) => {
		userMenuOpen = false;
		console.log('User menu action:', itemId);
	};
</script>

<div class="sticky top-0 z-50 border-b border-bb-blue/10 bg-bb-bg shadow-sm backdrop-blur-md">
	<div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
		<div class="flex h-16 items-center justify-between">
			<a href="/" class="flex items-center space-x-3">
				<div
					class="flex h-9 w-9 items-center justify-center rounded-full bg-gradient-to-br from-bb-blue to-bb-moss shadow-md"
				>
					<Sparkles class="h-5 w-5 text-white" />
				</div>
				<span
					class="hidden bg-gradient-to-r from-bb-blue-dark to-bb-moss bg-clip-text text-xl font-bold text-transparent sm:block"
				>
					BrainBloom
				</span>
			</a>

			<div class="hidden items-center space-x-1 md:flex">
				{#each navItems as item}
					<a
						href={item.href}
						on:click={() => handleNavClick(item.id)}
						class="flex items-center gap-2 rounded-lg px-4 py-2 transition-all {currentPage ===
						item.id
							? 'bg-bb-blue/10 font-medium text-bb-blue-dark'
							: 'text-bb-ink/70 hover:bg-bb-blue/5 hover:text-bb-ink'}"
					>
						<svelte:component this={item.icon} class="h-4 w-4" />
						<span class="text-sm">{item.label}</span>
					</a>
				{/each}
			</div>

			{#if !signedIn}
				<div class="flex gap-4">
					<button class="px-4 py-2 text-bb-ink transition-opacity hover:opacity-70">
						Sign In
					</button>
					<button
						class="rounded-full bg-gradient-to-r from-bb-blue to-bb-moss px-6 py-2 text-white transition-all hover:scale-105 hover:shadow-lg"
					>
						Get Started
					</button>
				</div>
			{/if}

			{#if signedIn}
				<div class="flex items-center gap-3">
					<button
						class="hidden items-center gap-2 rounded-lg bg-gradient-to-r from-bb-blue to-bb-moss px-4 py-2 text-sm font-medium text-white transition-all hover:scale-105 hover:shadow-lg sm:flex"
					>
						<PenLine class="h-4 w-4" />
						<span>New Idea</span>
					</button>

					<div class="relative">
						<button
							on:click={toggleUserMenu}
							class="flex h-9 w-9 items-center justify-center rounded-full bg-gradient-to-br from-bb-coral to-bb-gold font-medium text-white transition-all hover:shadow-md"
						>
							JD
						</button>

						{#if userMenuOpen}
							<div
								class="absolute right-0 mt-2 w-48 animate-in rounded-lg border border-bb-blue/10 bg-bb-paper py-1 shadow-xl"
							>
								{#each userMenuItems as item}
									<button
										on:click={() => handleUserMenuClick(item.id)}
										class="flex w-full items-center gap-3 px-4 py-2 text-sm text-bb-ink/80 transition-colors hover:bg-bb-blue/5 hover:text-bb-ink"
									>
										<svelte:component this={item.icon} class="h-4 w-4" />
										<span>{item.label}</span>
									</button>
								{/each}
							</div>
						{/if}
					</div>

					<button
						on:click={toggleMobileMenu}
						class="flex h-9 w-9 items-center justify-center rounded-lg text-bb-ink transition-colors hover:bg-bb-blue/5 md:hidden"
					>
						{#if mobileMenuOpen}
							<X class="h-5 w-5" />
						{:else}
							<Menu class="h-5 w-5" />
						{/if}
					</button>
				</div>
			{/if}
		</div>
	</div>

	<!-- Mobile Menu -->
	{#if mobileMenuOpen}
		<div class="border-t border-bb-blue/10 bg-bb-paper/98 backdrop-blur-md md:hidden">
			<div class="space-y-1 px-4 py-3">
				{#each navItems as item}
					<button
						on:click={() => handleNavClick(item.id)}
						class="flex w-full items-center gap-3 rounded-lg px-4 py-3 transition-all {currentPage ===
						item.id
							? 'bg-bb-blue/10 font-medium text-bb-blue-dark'
							: 'text-bb-ink/70 hover:bg-bb-blue/5 hover:text-bb-ink'}"
					>
						<svelte:component this={item.icon} class="h-5 w-5" />
						<span>{item.label}</span>
					</button>
				{/each}

				<!-- Mobile New Idea Button -->
				<button
					class="mt-2 flex w-full items-center justify-center gap-2 rounded-lg bg-gradient-to-r from-bb-blue to-bb-moss px-4 py-3 font-medium text-white"
				>
					<PenLine class="h-5 w-5" />
					<span>New Idea</span>
				</button>
			</div>
		</div>
	{/if}
</div>

<svelte:window
	on:click={(e) => {
		if (userMenuOpen && !(e.target as HTMLElement).closest('.relative')) {
			userMenuOpen = false;
		}
	}}
/>

<style>
	@keyframes slide-in {
		from {
			opacity: 0;
			transform: translateY(-10px);
		}
		to {
			opacity: 1;
			transform: translateY(0);
		}
	}

	.animate-in {
		animation: slide-in 0.2s ease-out;
	}
</style>
