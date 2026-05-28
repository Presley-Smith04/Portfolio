<script>
  import { base } from '$app/paths';
  import { onMount } from 'svelte';

  let audio;
  let isPlaying = true;
  let isMuted = false;
  let open = false;
  let volume = 0.5;

  let tracks = [
    `${base}/assets/music/arc-lofi.mp3`,
    `${base}/assets/music/clear-final-long.mp3`,
    `${base}/assets/music/cyber-rock.mp3`,
    `${base}/assets/music/flute.mp3`,
    `${base}/assets/music/lofi.mp3`,
    `${base}/assets/music/ooooo.mp3`,
    `${base}/assets/music/pop rock.mp3`,
    `${base}/assets/music/pretzel.mp3`
  ];

  let current = 0;

  function loadTrack(index) {
    if (!audio) return;

    audio.src = tracks[index];
    audio.load();

    audio.volume = volume;

    if (isPlaying) {
      audio.play();
    }
  }

  function nextTrack() {
    current = (current + 1) % tracks.length;
    loadTrack(current);
  }

  function togglePlay() {
    if (!audio) return;

    if (audio.paused) {
      audio.play();
      isPlaying = true;
    } else {
      audio.pause();
      isPlaying = false;
    }
  }

  function toggleMute() {
    if (!audio) return;

    audio.muted = !audio.muted;
    isMuted = audio.muted;
  }

  function updateVolume(e) {
    volume = e.target.value;

    if (audio) {
      audio.volume = volume;
    }
  }

  onMount(() => {
    loadTrack(current);
  });
</script>

<!-- hidden audio element -->
<audio
  bind:this={audio}
  on:ended={nextTrack}
  autoplay
></audio>

<!-- Settings Button -->
<button
  class="fixed bottom-6 right-6 z-50 bg-pink-500 text-black px-4 py-2 rounded-full shadow-lg hover:scale-105 transition"
  on:click={() => (open = !open)}
>
  ⚙ Music
</button>

<!-- Popup -->
{#if open}
  <div class="fixed bottom-20 right-6 z-50 w-64 bg-black/70 backdrop-blur-lg border border-white/20 p-4 rounded-2xl shadow-xl text-white">

    <h3 class="font-bold mb-3">Music Controls</h3>

    <div class="flex flex-col gap-2">

      <button class="bg-white/10 p-2 rounded hover:bg-white/20" on:click={togglePlay}>
        {isPlaying ? 'Pause' : 'Play'}
      </button>

      <button class="bg-white/10 p-2 rounded hover:bg-white/20" on:click={toggleMute}>
        {isMuted ? 'Unmute' : 'Mute'}
      </button>

      <button class="bg-white/10 p-2 rounded hover:bg-white/20" on:click={nextTrack}>
        Skip Track
      </button>

      <div class="mt-3">
        <p class="text-xs mb-1 text-gray-300">Volume</p>

        <input
          type="range"
          min="0"
          max="1"
          step="0.01"
          bind:value={volume}
          on:input={updateVolume}
          class="w-full"
        />
      </div>

    </div>

    <p class="text-xs text-gray-300 mt-3">
      Track {current + 1} / {tracks.length}
    </p>

  </div>
{/if}