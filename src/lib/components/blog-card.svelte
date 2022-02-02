<script>
	export let slug = '';
	export let name = '';
</script>

<div class="flex-auto w-full h-1/2 rounded-2xl bg-zinc-900 font-Inter my-5 mx-5">
	<a class="text-white font-bold text-3xl" href={slug}>{name}</a>
</div>

<style>
	@media only screen and (min-width: 600px) {
		div:nth-child(1n + 0) {
			width: 60%;
			height: 40%;
		}
		div:nth-child(2n + 0) {
			width: 32%;
			height: 40%;
		}
		div:nth-child(3n + 0) {
			width: 32%;
			height: 40%;
		}
		div:nth-child(4n + 0) {
			width: 60%;
			height: 40%;
		}
	}
</style>
