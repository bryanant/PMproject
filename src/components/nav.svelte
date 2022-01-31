<nav>
    {#each data.sections as navItem}
        <a class="navItem" href="{navItem.slug}">{navItem.name}</a>
    {/each}
</nav>

<script>
import * as data from '../cms_export.json';

</script>

<style>
    nav {
        z-index: 10;

        position: fixed;
        inset: 0;
        margin: 0 auto;

        display: flex;
        justify-content: center;
        align-items: center;

        height: 4rem;
        width: 100%;
        max-width: 1200px;
    }

    .navItem {
        display: flex;
        justify-content: center;
        align-items: center;
        flex: 1 1 auto;

        height: 4rem;

        background-color: white;
        color: black;

        font-size: 1.5rem;
        font-weight: bold;
        text-transform: uppercase;

        transition: all 100ms ease-in-out;
    }

    .navItem:hover {
        color: white;
        background-color: black;
        text-decoration: none;
    }
</style>