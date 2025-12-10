<script>
  import { OtherProjects } from '$lib/data/other-projects.js';
  import ProjectCard from './ProjectCard.svelte';
</script>

<div class="grid gap-6 grid-cols-1 sm:grid-cols-2 lg:grid-cols-3">
  {#each OtherProjects as project}
    <ProjectCard
      title={project.title}
      description={project.description}
      image={project.image}
      slug={project.slug}
      link={project.link}
    />
  {/each}
</div>
