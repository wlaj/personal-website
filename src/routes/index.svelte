<script context="module">
	import { client } from '$lib/graphql-client';
	import SourceCard from '$lib/components/source-card.svelte';
	import { sourcesQuery } from '$lib/graphql-queries';

	export const load = async () => {
		const { sources } = await client.request(sourcesQuery);

		return {
			props: {
				sources
			}
		};
	};
</script>

<script>
	export let sources;
</script>

<svelte:head>
	<title>Wlaj</title>
</svelte:head>

<div class="flex flex-nowrap container min-w-full min-h-screen items-center justify-center">
	<div class="bg-zinc-900 rounded-3xl cursor-pointer flex flex-row p-3">
		{#each sources as { name, slug }}
			<SourceCard {name} {slug} />
		{/each}
	</div>
</div>
