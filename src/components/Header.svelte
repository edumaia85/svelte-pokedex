<script>
    import logoImg from "../assets/pokeball-logo.png";
</script>

<header class="header">
    <nav>
        <a href="/">
            <img src={logoImg} alt="" height="30" width="30" />
            Pokedex
        </a>
    </nav>
</header>

<style>
    .header {
        width: 100%;
        height: 40px;
        background: black;

        display: flex;
    }

    .header nav {
        width: 100%;
        height: 100%;

        display: flex;
        align-items: center;
    }

    .header nav a {
        color: #fff;
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 0.5rem;
    }
</style>
