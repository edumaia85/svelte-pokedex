<script>
  import Header from "../components/Header.svelte";
  export let title;
</script>

<svelte:head>
  <title>{title}</title>
</svelte:head>

<Header />

<main class="container">
  <slot />
</main>

<style>
    .container {
        flex: 1;
    }
</style>
