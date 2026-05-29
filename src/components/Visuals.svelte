<script>
	import { onMount } from 'svelte';
	import { base } from '$app/paths';
	let open = false;

	//visual effects
	let hue = 0;
	let blur = 0;
	let invert = 0;
	let saturate = 100;

	//random effects
	let rippleMode = false;
	let quackMode = false;
	let sparkMode = false;
	let shakeMode = false;

	let quack;

	$: filterStyle = `
    hue-rotate(${hue}deg)
    blur(${blur}px)
    invert(${invert}%)
    saturate(${saturate}%)
  `;

	function handleClick(e) {
		//ripple function
		if (rippleMode) {
			const ripple = document.createElement('div');
			ripple.className = 'ripple';
			ripple.style.left = `${e.clientX}px`;
			ripple.style.top = `${e.clientY}px`;

			document.body.appendChild(ripple);

			setTimeout(() => {
				ripple.remove();
			}, 1000);
		}

		//quack function
		if (quackMode && quack) {
			quack.currentTime = 0;
			quack.play();
		}

		//spark function
		if (sparkMode) {
			for (let i = 0; i < 0; i++) {
				const spark = document.createElement('div');
				spark.className = 'spark';
				spark.style.left = `${e.clientX}px`;
				spark.style.top = `${e.clientY}px`;

				spark.style.transform = `
          translate(
            ${(Math.random() - 0.5) * 120}px,
            ${(Math.random() - 0.5) * 120}px
          )
        `;

				document.body.appendChild(spark);

				setTimeout(() => {
					spark.remove();
				}, 1000);
			}
		}

		//shake
		if (shakeMode) {
			document.body.classList.add('screen-shake');

			setTimeout(() => {
				document.body.classList.remove('screen-shake');
			}, 300);
		}
	}

	onMount(() => {
		window.addEventListener('click', handleClick);

		quack = new Audio(`${base}/assets/quack.mp3`);

		return () => {
			window.removeEventListener('click', handleClick);
		};
	});
</script>

<!-- global filter overlay for the screen -->
<div
	class="pointer-events-none fixed inset-0 z-[9998]"
	style={`backdrop-filter: ${filterStyle}; -webkit-backdrop-filter: ${filterStyle};`}
></div>

<!-- button for effects -->
<button
	class="fixed right-6 bottom-24 z-[9999] rounded-full bg-cyan-400 px-4 py-2 text-black shadow-lg transition hover:scale-105"
	on:click={() => (open = !open)}
>
	🥸 FX
</button>

<!-- effects pannel -->
{#if open}
	<div
		class="fixed right-6 bottom-40 z-[9999] w-72 rounded-2xl border
         border-white/20 bg-black/70 p-5 text-white shadow-xl backdrop-blur-xl"
	>
		<h3 class="mb-4 text-lg font-bold">Visual Effects</h3>

		<!-- Hue -->
		<div class="mb-4">
			<div class="mb-1 flex justify-between text-sm">
				<span>Hue</span>
				<span>{hue}°</span>
			</div>

			<input type="range" min="0" max="360" bind:value={hue} class="w-full" />
		</div>

		<!-- Blur -->
		<div class="mb-4">
			<div class="mb-1 flex justify-between text-sm">
				<span>Blur</span>
				<span>{blur}px</span>
			</div>

			<input type="range" min="0" max="10" step="0.1" bind:value={blur} class="w-full" />
		</div>

		<!-- Invert -->
		<div class="mb-4">
			<div class="mb-1 flex justify-between text-sm">
				<span>Negative</span>
				<span>{invert}%</span>
			</div>

			<input type="range" min="0" max="100" bind:value={invert} class="w-full" />
		</div>

		<!-- Saturation -->
		<div class="mb-2">
			<div class="mb-1 flex justify-between text-sm">
				<span>Saturation</span>
				<span>{saturate}%</span>
			</div>

			<input type="range" min="0" max="300" bind:value={saturate} class="w-full" />
		</div>
		<div class="mt-5 border-t border-white/10 pt-4">
			<h4 class="mb-3 font-bold">Fun Effects</h4>

			<label class="mb-2 flex items-center gap-2">
				<input type="checkbox" bind:checked={rippleMode} />
				Ripple
			</label>

			<label class="mb-2 flex items-center gap-2">
				<input type="checkbox" bind:checked={quackMode} />
				Quack
			</label>

			<label class="mb-2 flex items-center gap-2">
				<input type="checkbox" bind:checked={sparkMode} />
				Sparks
			</label>

			<label class="flex items-center gap-2">
				<input type="checkbox" bind:checked={shakeMode} />
				Shake
			</label>
		</div>
	</div>
{/if}
