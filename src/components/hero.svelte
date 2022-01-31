<header class="hero content">
    <h1>{title}</h1>
    <h2>{tagline}</h2>
</header>

<script>
    export let title;
    export let tagline;
</script>

<style>
.hero {
    display: flex;
    flex-flow: column nowrap;
    justify-content: center;

    height: 90vh;
    width: 100%;

    background-color: transparent;
}

h1 {
    padding: 2rem;
    background-color: white;
    font-size: 10rem;
    line-height: 8rem;
    margin: 0;
}

h2 {
    padding: 2rem;
    background-color: white;
    color: gray;
    font-size: 4rem;
    line-height: 2rem;
    margin: 0;
}
</style>