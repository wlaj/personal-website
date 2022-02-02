<script context="module">
    import ProjectCard from '$lib/components/project-card.svelte'
    import { client } from '$lib/graphql-client'
    import { projectsQuery } from '$lib/graphql-queries'
  
    export const load = async () => {
      const { projects } = await client.request(projectsQuery)
  
      return {
        props: {
          projects,
        },
      }
    }
  </script>
  
  <script>
    export let projects
  </script>
  
  <svelte:head>
    <title>Case studies</title>
  </svelte:head>
  
  <h1 class="font-bold p-5 text-5xl container m-auto">
    Recent projects
  </h1>
  <div
    class="grid m-auto container lg:grid-cols-2"
  >
    {#each projects as { name, slug, description, image }, index}
      <ProjectCard
        {name}
        {description}
        url={image[0].url}
        {index}
        {slug}
      />
    {/each}
  </div>