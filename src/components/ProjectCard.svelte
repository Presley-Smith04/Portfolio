<script>
  export let title;
  export let description;
  export let image;
  export let slug;
</script>

<a href={`/projects/${slug}`} 
   class="block transform transition duration-500 hover:-translate-y-3 hover:rotate-2 hover:scale-105 hover:shadow-[0_8px_30px_rgba(255,192,203,0.6)]">
  <div class="bg-white text-black rounded-2xl overflow-hidden shadow-lg h-full flex flex-col 
              transition-all duration-500 hover:bg-pink-200 hover:text-rose-800 hover:border-4 hover:border-amber-400">
    <img src="{image}" alt={title} 
         class="w-full h-60 object-cover transition-transform duration-500 hover:scale-110" />
    <div class="p-6 flex flex-col flex-grow">
      <h3 class="text-2xl font-bold mb-3">{title}</h3>
      <p class="text-base text-gray-700 flex-grow">{description}</p>
    </div>
  </div>
</a>
