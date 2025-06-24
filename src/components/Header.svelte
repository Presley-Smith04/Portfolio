<script>
  import { onMount } from 'svelte';
  import { tweened } from 'svelte/motion';
  import { cubicOut } from 'svelte/easing';

  let showNav = false;

  onMount(() => {
    const handleScroll = () => {
      showNav = window.scrollY > 10;
    };

    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  });
</script>



<style>
  nav {
    /* start hidden */
    transform: translateY(-100%);
    transition: transform 0.35s cubic-bezier(0.4, 0, 0.2, 1), opacity 0.35s ease;
    opacity: 0;
  }

  nav.visible {
    transform: translateY(0);
    opacity: 1;
  }
</style>

<nav class={`fixed top-0 left-0 w-full z-50 backdrop-blur-md bg-black bg-opacity-40 shadow-lg ${showNav ? 'visible' : ''}`}>
  <div class="max-w-6xl mx-auto px-8 py-6 flex justify-between items-center text-white">
    <h1 class="text-4xl font-extrabold cursor-default select-none">Presley Smith</h1>
    <ul class="flex gap-10 text-2xl font-medium">
      <li>
        <a href="#showcase" class="hover:text-indigo-400 transform transition-transform duration-200 hover:scale-110">Showcase</a>
      </li>
      <li>
        <a href="mailto:presleysmith04@gmail.com?subject=Inquiry for Presley Smith&body=" class="hover:text-indigo-400 transform transition-transform duration-200 hover:scale-110">Contact</a>
      </li>
      <li>
        <a href="https://github.com/Presley-Smith04" target="_blank" rel="noopener" class="hover:text-indigo-400 transform transition-transform duration-200 hover:scale-110">GitHub</a>
      </li>
      <li>
        <a href="https://www.linkedin.com/in/presley-smith-46261324a" target="_blank" rel="noopener" class="hover:text-indigo-400 transform transition-transform duration-200 hover:scale-110">LinkedIn</a>
      </li>
    </ul>
  </div>
</nav>

