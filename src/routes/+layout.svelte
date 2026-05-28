<script>
  import "../app.css";
  import MusicPlayer from "../components/MusicPlayer.svelte";

  let { children } = $props();
</script>

{@render children()}

<MusicPlayer />