<script lang="ts">
	import KitBook from '$lib/components/core/main.svelte';
	import { page } from '$app/stores';
	$: data = $page.data as {
		md: string;
		toc: {
			degree: number;
			name: string;
		}[];
	};
	const sectionsMap = new Map<string, string[]>([
		[
			'Create split app',
			[
				'introduction',
				'why split',
				'installation',
				'folder structure',
				'faq',
				'other recommendations'
			]
		],
		[
			'Usage',
			['First steps', 'Svelte kit', 'Typescript', 'Prisma', 'Lucia', 'Tailwind', 'Zod', 'Sockets']
		],
		['Deployment', ['Vercel', 'Netlify', 'Render', 'Docker']]
	]);
</script>

<KitBook
	{sectionsMap}
	{data}
	navBarHeight={80}
	pathname={$page.url.pathname}
	githubLink="links .link "
	npmLink="links .link "
	discordLink="v"
	navlinks={[
		{ label: 'example', href: 'jjj' },
		{ label: 'test', href: 'jjj' },
		{ label: 'home', href: '/' }
	]}
/>
