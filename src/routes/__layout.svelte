<script>
	import '../style.css';
    import Navbar from '$lib/components/Navbar.svelte';
</script>

<main class="w-screen min-h-screen flex flex-col">
    <Navbar />
    <slot />
</main>