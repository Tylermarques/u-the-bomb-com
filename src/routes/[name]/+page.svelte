<script lang="ts">
	export let data;
	import { onMount } from 'svelte';
	import confetti from 'canvas-confetti';

	let name = atob(data.name_hash);
	function randomInRange(min: number, max: number) {
		return Math.random() * (max - min) + min;
	}

	let defaults = { startVelocity: 30, spread: 360, ticks: 60, zIndex: 0 };
	function start_fireworks() {
		confetti({
			...defaults,
			particleCount: 100,
			origin: { x: randomInRange(0.2, 0.8), y: Math.random() - 0.2 }
		});
	}

	onMount(() => {
		setInterval(start_fireworks, 378);
		setInterval(start_fireworks, 609);
	});
</script>

<div class="flex flex-col items-center space-y-10 justify-center h-screen">
	<h1 class="text-8xl font-bold">{name}</h1>
	<div class="flex flex-row items-center text-4xl font-bold">
		<p class="animate-bounce">💣</p>
		<p>U the Bomb.com</p>
		<p class="animate-bounce">💣</p>
	</div>
</div>
