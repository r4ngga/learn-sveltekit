<script>
	import Nav from './Nav.svelte';
</script>

<div class="w-screen">
	<Nav />

	<main class="w-screen">
		<slot />
	</main>
</div>
