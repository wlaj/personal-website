<script>
	export let slug = '';
	export let name = '';
</script>

<div class="px-14 py-7 hover:bg-zinc-800 hover:rounded-xl">
	<a class="text-zinc-50 font-semibold text-3xl hover:text-zinc-200" href={slug}>{name}</a>
</div>
