<script context="module">
	import { client } from '$lib/graphql-client';
	import SourceCard from '$lib/components/source-card.svelte'
	import { sourcesQuery } from '$lib/graphql-queries';

	export const load = async () => {
		const { sources } = await client.request(sourcesQuery)

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

{#each sources as { name, slug }}
	<SourceCard {name} {slug} />
{/each}
