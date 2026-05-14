<script lang="ts">
	import favicon from '$lib/assets/favicon.svg';
	import '../app.css'
	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<title>Coddo</title>
	<meta name="description" content="Hi, I'm Coddo, a 20-year-old software and web developer">
</svelte:head>

{@render children()}
