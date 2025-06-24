<script context="module">
  import { projects } from '$lib/data/projects.js';

  /** @type {import('./$types').PageLoad} */
  export function load({ params }) {
    const project = projects.find(p => p.slug === params.slug);
    if (!project) {
      throw error(404, "Project not found");
    }
    return { project };
  }
</script>

<script>
  export let data;
  const { project } = data;
</script>

<main class="max-w-4xl mx-auto py-20 px-4 text-white">
  <h1 class="text-4xl font-bold mb-4">{project.title}</h1>
  <img src={project.image} alt={project.title} class="rounded-lg mb-8 w-full max-h-[400px] object-cover" />
  <p class="text-lg">{project.description}</p>

  <a href="/" class="mt-10 inline-block text-indigo-400 underline">← Back to Home</a>
</main>
