<script>
    import Character from "$lib/character.svelte"
</script>

<style>

    .grid{
        display:grid;
        grid-template-columns:1fr 1fr 1fr;
        gap:30px;
        background-color: rgb(39, 43, 51);
    }

</style>

<div class="grid">
    
    {#each Array(6) as _}
        <Character />
    {/each}

</div>
