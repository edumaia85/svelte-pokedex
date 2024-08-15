<script>
    export let name;
    export let image;
    export let type;
</script>

<div class="pokemon-card-container">
    <img src={image} alt={name} />
    <h2>{name}</h2>
    <p>Tipo {type}</p>
</div>

<style>
    .pokemon-card-container {
        border: 1px solid #ccc;
        border-radius: 8px;
        padding: 16px;
        text-align: center;
        width: 150px;
    }
    img {
        width: 100px;
        height: 100px;
    }
</style>
