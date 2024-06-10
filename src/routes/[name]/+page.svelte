<script lang="ts">
	export let data;
	import { onMount } from 'svelte';
	import confetti from 'canvas-confetti';
	import BackArrow from '$lib/components/BackArrow.svelte';

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

	function stop_fireworks() {
		// Get a reference to the last interval + 1
		const interval_id = window.setInterval(function () {}, Number.MAX_SAFE_INTEGER);

		// Clear any timeout/interval up to that id
		for (let i = 1; i < interval_id; i++) {
			window.clearInterval(i);
		}
	}

	onMount(() => {
		stop_fireworks();
		setInterval(start_fireworks, 378);
		setInterval(start_fireworks, 609);
	});
</script>

<div>
	<BackArrow />
	<div class="flex flex-col items-center space-y-10 justify-center h-screen">
		<div class="text-5xl md:text-6xl lg:text-8xl flex text-center flex-row items-center font-bold">
			<p>{name}</p>
		</div>
		<div class="text-2xl md:text-4xl lg:text-5xl flex flex-row items-center font-bold">
			<p class="animate-bounce">💣</p>
			<p>U the Bomb.com</p>
			<p class="animate-bounce">💣</p>
		</div>
	</div>
</div>
