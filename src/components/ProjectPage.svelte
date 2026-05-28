<script>
  import { base } from '$app/paths';
  import { onMount } from 'svelte';

  export let title;
  export let headline;
  export let image;
  export let tags;
  export let content;
  export let projectLink;

  onMount(() => {
    if (window.particlesJS) {
      window.particlesJS.load(
        'particles-js',
        `${base}/assets/particles.json`
      );
    }
  });
</script>

<section class="relative min-h-screen overflow-hidden bg-[#12091a] text-white">

  <!-- Particles -->
  <div
    id="particles-js"
    class="absolute inset-0 z-0"
  ></div>

  <!-- Dark Overlay -->
  <div class="absolute inset-0 bg-black/40 z-0"></div>

  <!-- Content -->
  <div class="relative z-10 max-w-3xl mx-auto px-6 py-24 flex flex-col items-center gap-8">

    <!-- Title Card -->
    <div
      class="w-full bg-white/10 backdrop-blur-lg rounded-3xl p-8
             border border-white/20 shadow-xl
             transition-all duration-300
             hover:-translate-y-2 hover:rotate-1"
    >
      <h1 class="text-5xl font-black text-pink-300 mb-4 text-center">
        {title}
      </h1>

      <h2 class="text-xl text-gray-200 text-center leading-relaxed">
        {headline}
      </h2>
    </div>

    <!-- Image Card -->
    <div
      class="w-full overflow-hidden rounded-3xl
             border border-white/20 shadow-xl
             transition-all duration-300
             hover:-translate-y-2 hover:-rotate-1"
    >
      <img
        src={base + image}
        alt={title}
        class="w-full object-cover max-h-[500px]"
      />
    </div>

    <!-- Tech Stack -->
    <div
      class="w-full bg-white/10 backdrop-blur-lg rounded-3xl p-6
             border border-white/20 shadow-xl
             transition-all duration-300
             hover:-translate-y-2 hover:rotate-1"
    >
      <h3 class="text-2xl font-bold text-amber-300 mb-3">
        Technologies Used
      </h3>

      <p class="text-lg text-gray-100 leading-relaxed">
        {tags}
      </p>
    </div>

    <!-- Content -->
    <div
      class="w-full bg-white/10 backdrop-blur-lg rounded-3xl p-8
             border border-white/20 shadow-xl
             transition-all duration-300
             hover:-translate-y-2 hover:-rotate-1"
    >
      <h3 class="text-2xl font-bold text-cyan-300 mb-5">
        Project Breakdown
      </h3>

      <p class="text-lg leading-loose text-gray-100 whitespace-pre-line">
        {content}
      </p>
    </div>

    <!-- Buttons -->
    <div class="flex gap-4 flex-wrap justify-center mt-4">

      <a
        href={projectLink}
        target="_blank"
        class="px-7 py-3 rounded-full bg-pink-500 text-white font-bold
               shadow-lg transition-all duration-300
               hover:scale-105 hover:-translate-y-1
               hover:bg-amber-400 hover:text-black"
      >
        View Project
      </a>

      <a
        href={base + '/'}
        class="px-7 py-3 rounded-full bg-white/10 backdrop-blur-lg
               border border-white/20 shadow-lg
               transition-all duration-300
               hover:scale-105 hover:-translate-y-1 hover:bg-white/20"
      >
        Back Home
      </a>

    </div>

  </div>
</section>