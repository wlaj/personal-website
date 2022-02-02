<script>
    export let url = ''
    export let name = ''
    export let slug = ''
    export let description = ''
  </script>
  
  <div class="m-5 rounded-xl bg-zinc-900">
    <img src={url} alt={name} class="rounded-t-lg" />
    <a href={`/projects/${slug}`}>
      <div
        class="p-5"
      >
        <h2 class="font-semibold lg:text-xl">{name}</h2>
        <p class="text-sm lg:text-xl text-zinc-400">
          {description.slice(0, 80)}...
        </p>
      </div>
    </a>
  </div>