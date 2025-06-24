<script>
  export let id = "";
  export let title = "";
  const githubUrl = "https://github.com/Presley-Smith04";
  const linkedinUrl = "https://www.linkedin.com/in/presley-smith-46261324a/";
  const emailAddress = "presleysmith04@gmail.com";
</script>



<footer
  {id}
  class="py-20 px-4 md:px-10 text-white bg-black text-center space-y-8"
>
  <div class="max-w-4xl mx-auto">
    <h2 class="text-4xl font-bold mb-6">{title}</h2>

    <slot />

    <p class="text-2xl mt-6">
      Contact me at: <a href={`mailto:${emailAddress}`} class="underline">{emailAddress}</a>
    </p>
  </div>

  <div class="flex justify-center space-x-12 text-4xl">
    <a
      href={githubUrl}
      target="_blank"
      rel="noopener noreferrer"
      aria-label="GitHub"
      class="hover:text-indigo-500 transition-colors duration-300"
    >
      <i class="fab fa-github"></i>
    </a>

    <a
      href={linkedinUrl}
      target="_blank"
      rel="noopener noreferrer"
      aria-label="LinkedIn"
      class="hover:text-indigo-500 transition-colors duration-300"
    >
      <i class="fab fa-linkedin"></i>
    </a>

    <a
      href={`mailto:${emailAddress}`}
      aria-label="Email"
      class="hover:text-indigo-500 transition-colors duration-300"
    >
      <i class="fas fa-envelope"></i>
    </a>
  </div>

  <p class="mt-12 text-sm text-gray-400">
    &copy; {new Date().getFullYear()} Presley Smith. All Rights Reserved.
  </p>
</footer>
