<script>
	import { goto } from '$app/navigation';
	let name = '';

	function updateURL() {
		goto('/' + btoa(name));
	}
</script>

<div class="flex items-center justify-center h-screen">
	<input
		type="text"
		bind:value={name}
		on:submit={updateURL}
		class="border p-2 rounded"
		placeholder="Give some kudos"
	/>
	<button on:click={updateURL}>Go</button>
</div>
