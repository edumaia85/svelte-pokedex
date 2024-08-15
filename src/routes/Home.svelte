<script>
    import { onMount } from "svelte";
    import PokemonCard from "../components/PokemonCard.svelte";
    import DefaultLayout from "../layouts/DefaultLayout.svelte";

    let pokemonList = [];
    let loading = true;

    onMount(async () => {
        try {
            const response = await fetch(
                "https://pokeapi.co/api/v2/pokemon?limit=150",
            );
            const data = await response.json();

            const detailedPokemons = await Promise.all(
                data.results.map(async (pokemon) => {
                    const res = await fetch(pokemon.url);
                    return res.json();
                }),
            );

            pokemonList = detailedPokemons;
        } catch (err) {
            console.log(err.message);
        } finally {
            loading = false;
        }
    });
</script>

<main>
    <DefaultLayout title="Pokedex - Página Inicial">
        {#if loading}
            <p>Carregando...</p>
        {:else}
            {#each pokemonList as pokemon}
                <PokemonCard
                    name={pokemon.name}
                    image={pokemon.sprites.front_default}
                    type={pokemon.types.map((typeInfo) => typeInfo.type.name)}
                />
            {/each}
        {/if}
    </DefaultLayout>
</main>
