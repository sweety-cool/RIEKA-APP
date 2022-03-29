<script>
	import Page from '../components/Pages.svelte';
</script>

<div class="p-8 max-w-6xl mx-auto">
	<Page />

	<slot />
</div>

<style>
	@tailwind base;
	@tailwind components;
	@tailwind utilities;
</style>
