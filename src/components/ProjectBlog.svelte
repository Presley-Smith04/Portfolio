<script>
  import { base } from '$app/paths';

  export let title;
  export let headline;
  export let image;
  export let tags;
  export let content;
  export let link;
  export let linkLabel;
</script>

<section class="min-h-screen py-20 px-6 bg-gradient-to-b from-pink-50 to-rose-100 text-gray-800">
  <div class="max-w-4xl mx-auto">

    <!-- Title -->
    <h1 class="text-4xl sm:text-5xl font-extrabold mb-4 text-rose-700">
      {title}
    </h1>

    <!-- Headline -->
    <h2 class="text-xl sm:text-2xl mb-8 text-gray-600">
      {headline}
    </h2>

    <!-- Image -->
    {#if image}
      <img 
        src="{base}{image}" 
        alt={title} 
        class="w-full rounded-2xl shadow-xl mb-10"
      />
    {/if}

    <!-- Tags -->
    {#if tags}
      <div class="mb-8 p-4 rounded-xl bg-white shadow-md border-2 border-amber-300">
        <h3 class="font-bold mb-2 text-rose-600">Tech Stack</h3>
        <p>{tags}</p>
      </div>
    {/if}

    <!-- Content -->
    <div class="text-lg leading-relaxed space-y-6">
      <p>{content}</p>
    </div>

    <!-- External Link -->
    {#if link}
      <div class="mt-10">
        <a 
          href={link} 
          target="_blank"
          class="inline-block px-6 py-3 rounded-full bg-rose-500 text-white font-semibold 
                 transition-all duration-300 hover:bg-amber-400 hover:text-black 
                 hover:scale-105 hover:shadow-lg"
        >
          {linkLabel}
        </a>
      </div>
    {/if}

  </div>
</section>
