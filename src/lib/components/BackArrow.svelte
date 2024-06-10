<script lang="ts">
	function goHome() {
		window.location.href = '/';
	}
</script>

<div on:mouseup={goHome} role="button" tabindex="0" class="backarrow absolute top-2, left-0">
	<svg width="2em" height="2em" viewBox="0 0 200 200" preserveAspectRatio="xMidYMid slice">
		<svg xmlns="http://www.w3.org/2000/svg" width="200" height="200" viewBox="0 0 24 24">
			<g
				fill="none"
				stroke="currentColor"
				stroke-linecap="round"
				stroke-linejoin="round"
				stroke-width="2"
			>
				<path class="arrowline" d="M21 12H9m4 4l-4-4l4-4" />
				<path class="backarrow-hover:arrowline" d="M12 3a9 9 0 1 0 0 18" />
			</g>
		</svg>
	</svg>
</div>

<style>
	@keyframes slightRight {
		0% {
			transform: translateX(0);
		}
		25% {
			transform: translateX(50px); /* Slide left */
		}
		50% {
			transform: translateX(50px); /* Pause */
		}
		100% {
			transform: translateX(-150px); /* Speed up to the right */
		}
	}
	.backarrow:hover .arrowline {
		animation: slightRight 2s infinite ease-in-out;
	}
</style>
