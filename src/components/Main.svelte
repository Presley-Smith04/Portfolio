<script>
    import { onMount } from "svelte";

    onMount(() => {
        particlesJS.load("particles-js", "assets/particles.json", function () {
            console.log("Callback - particles.js config loaded");
        });
    });
</script>


<section
    class="relative h-screen flex items-center justify-center overflow-hidden text-white"
>
    <!--particles-->
    <div id="particles-js" class="absolute inset-0 z-0"></div>

    <!--me-->
    <img
        src="/assets/result.png"
        alt="Your portrait"
        class="z-10 w-40 h-40 md:w-56 md:h-56 object-cover object-[100%_10%] rounded-full border-4 border-white shadow-xl mb-6"
    />

    <!--content-->
    <div class="z-10 text-center">
        <h1 class="text-5xl md:text-7xl font-bold">Presley Smith</h1>
        <p class="mt-4 text-lg md:text-xl">
            Game Dev • Web Dev • UI/UX • Programmer
        </p>
        <p class="mt-8 animate-bounce text-gray-400">↓ scroll</p>
    </div>
</section>
