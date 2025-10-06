<script lang="ts">
	import JobCard from '$lib/components/job-card.svelte';
	import Toolbar from '$lib/components/toolbar.svelte';
	import { Search } from 'lucide-svelte';
	import { Input } from '$lib/components/ui/input/index.js';

	let searchQuery = $state('');
	let selectedType = $state('all');
	let selectedLocation = $state('all');

	const jobs = [
		{
			id: 1,
			title: 'Senior Frontend Engineer',
			company: 'Vercel',
			location: 'Remote',
			type: 'Full-time',
			salary: '$140k - $200k',
			logo: '/placeholder.svg?height=48&width=48',
			tags: ['React', 'TypeScript', 'Next.js'],
			posted: '2 days ago',
			link: '#',
			description:
				'We are looking for a Senior Frontend Engineer to join our team and help build the future of web development. You will work on cutting-edge projects using React, TypeScript, and Next.js.'
		},
		{
			id: 2,
			title: 'Product Designer',
			company: 'Stripe',
			location: 'San Francisco, CA',
			type: 'Full-time',
			salary: '$130k - $180k',
			logo: '/placeholder.svg?height=48&width=48',
			tags: ['Figma', 'UI/UX', 'Design Systems'],
			posted: '3 days ago',
			link: '#',
			description:
				'Join our design team to create beautiful and intuitive user experiences. You will work closely with engineers and product managers to design and ship features that millions of users love.'
		},
		{
			id: 3,
			title: 'Backend Engineer',
			company: 'Supabase',
			location: 'Remote',
			type: 'Full-time',
			salary: '$120k - $170k',
			logo: '/placeholder.svg?height=48&width=48',
			tags: ['Node.js', 'PostgreSQL', 'Go'],
			posted: '5 days ago',
			link: '#',
			description:
				'Help us build the open source Firebase alternative. You will work on our backend infrastructure, APIs, and database systems to power millions of applications worldwide.'
		},
		{
			id: 4,
			title: 'DevOps Engineer',
			company: 'Railway',
			location: 'Remote',
			type: 'Full-time',
			salary: '$130k - $190k',
			logo: '/placeholder.svg?height=48&width=48',
			tags: ['Kubernetes', 'AWS', 'Docker'],
			posted: '1 week ago',
			link: '#',
			description:
				'We are seeking a DevOps Engineer to help us scale our infrastructure and improve our deployment pipelines. You will work with Kubernetes, AWS, and Docker to ensure our platform is reliable and performant.'
		},
		{
			id: 5,
			title: 'Full Stack Developer',
			company: 'Linear',
			location: 'Remote',
			type: 'Contract',
			salary: '$100k - $150k',
			logo: '/placeholder.svg?height=48&width=48',
			tags: ['React', 'GraphQL', 'Node.js'],
			posted: '1 week ago',
			link: '#',
			description:
				'Join us as a contract Full Stack Developer to help build new features for our project management tool. You will work with React, GraphQL, and Node.js to create fast and delightful user experiences.'
		},
		{
			id: 6,
			title: 'Mobile Engineer',
			company: 'Notion',
			location: 'New York, NY',
			type: 'Full-time',
			salary: '$140k - $200k',
			logo: '/placeholder.svg?height=48&width=48',
			tags: ['React Native', 'iOS', 'Android'],
			posted: '2 weeks ago',
			description:
				'Help us build the best mobile experience for Notion. You will work on our React Native app to bring the power of Notion to iOS and Android users around the world.'
		}
	];

	const filteredJobs = () => {
		return jobs.filter((job) => {
			const matchesSearch =
				searchQuery === '' ||
				job.title.toLowerCase().includes(searchQuery.toLowerCase()) ||
				job.company.toLowerCase().includes(searchQuery.toLowerCase()) ||
				job.tags.some((tag) => tag.toLowerCase().includes(searchQuery.toLowerCase()));

			const matchesType = selectedType === 'all' || job.type === selectedType;
			const matchesLocation =
				selectedLocation === 'all' ||
				(selectedLocation === 'remote' && job.location === 'Remote') ||
				(selectedLocation === 'onsite' && job.location !== 'Remote');

			return matchesSearch && matchesType && matchesLocation;
		});
	};
</script>

<div
	class="min-h-screen items-center bg-background bg-gradient-to-b from-gray-900 to-gray-800 pt-24"
>
	<main class="mx-auto max-w-7xl px-4 py-8 sm:px-6 lg:px-8">
		<div class="mb-8 space-y-6">
			<div class="flex flex-col gap-4 lg:flex-row lg:items-center lg:justify-between">
				<div class="relative flex-1">
					<Search class="absolute top-1/2 left-4 size-5 -translate-y-1/2 text-white/80" />
					<Input
						type="text"
						placeholder="Search jobs, companies, or skills..."
						bind:value={searchQuery}
						class="w-full border border-cyan-700 bg-gray-950 pl-12 text-white placeholder:text-white/50 focus:border-cyan-400"
					/>
				</div>
				<Toolbar bind:selectedType bind:selectedLocation />
			</div>
		</div>

		<div class="space-y-4">
			<div class="mb-4 flex items-center justify-between">
				<p class="text-sm text-white/70">
					{filteredJobs().length}
					{filteredJobs().length === 1 ? 'job' : 'jobs'} found
				</p>
			</div>

			{#each filteredJobs() as job (job.id)}
				<JobCard {job} />
			{:else}
				<div class="rounded-lg p-12 text-center">
					<p class="text-white">No jobs found matching your criteria.</p>
				</div>
			{/each}
		</div>
	</main>
</div>
