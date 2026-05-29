<script>
	import '../app.css';
	import MusicPlayer from '../components/MusicPlayer.svelte';
	import Visuals from '../components/Visuals.svelte';

	let { children } = $props();
</script>

{@render children()}

<MusicPlayer />
<Visuals />
