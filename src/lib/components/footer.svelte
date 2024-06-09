<script>
	import { onMount } from 'svelte';
	import names from '$lib/data/names.json';

	let random_name = names.names[Math.floor(Math.random() * names.names.length)];
	let random_phase = names.phases[Math.floor(Math.random() * names.phases.length)];
	onMount(() => {
		setInterval(() => {
			random_name = names.names[Math.floor(Math.random() * names.names.length)];
		}, 1000);

		setInterval(() => {
			random_phase = names.phases[Math.floor(Math.random() * names.phases.length)];
		}, 1000);
	});
</script>

<div class="absolute bottom-0 left-0 right-0 h-10 flex flex-row items-center justify-center">
	<h1>{random_phase}: {random_name}</h1>
</div>
