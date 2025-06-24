<script>
    export let id = '';
    export let title = '';
</script>

 
<section id={id} class="py-20 px-4 md:px-10 bg-white text-black">
    <div class="max-w-4xl mx-auto">
        <h2 class="text-3xl font-bold mb-8">{title}</h2>
        <slot />
    </div>
</section>



<!--use like this;

<Step id="about" title="About Me">
  <p>Hi! I'm a web dev with a passion for creativity...</p>
</Step>

-->