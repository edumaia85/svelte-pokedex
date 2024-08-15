<script>
    import Router from "svelte-spa-router";
    import Home from "./routes/Home.svelte";
    import NotFound from "./routes/NotFound.svelte";
    import Pokemon from "./routes/Pokemon.svelte";

    const routes = {
        "/": Home,
        "/pokemon/:name": Pokemon,
        "*": NotFound,
    };
</script>

<main>
    <Router {routes} />
</main>

<style>
</style>
