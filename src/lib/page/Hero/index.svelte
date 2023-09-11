<script>
    import MediaQuery from "$lib/components/MediaQuery.svelte";
    import Web from "./web.svelte";
    import Responsive from "./responsive.svelte";
</script>

<MediaQuery query="(min-width: 1024px)" let:matches>
    {#if matches}
        <Web/>
    {:else}
        <Responsive />
    {/if}
</MediaQuery>