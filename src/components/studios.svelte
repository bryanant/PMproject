<section class="opaqueBg">
    <div class="panelContent">
        <h2>Our Studios</h2>

        <p>Voluptate ham hock ea, officia magna picanha filet mignon cow. Veniam alcatra pork chop, strip steak pork belly bacon culpa quis consequat drumstick biltong commodo sunt shoulder frankfurter. Doner do meatball kielbasa.</p>
    </div>

    <div class="studios panelContent">
        {#each data.studios as studio}
            <button
                class="card buttonStyle"
                data-active="{active === studio.id}"
                on:click={() => setActiveStudio(studio.id) }
            >
                {studio.name}
            </button>
        {/each}
    </div>

</section>

<section class="content" id="gamesPanel">
    {#each data.studios as studio}
        <Games studio={studio.id} active={studio.id === active}></Games>
    {/each}
</section>


<script>
import * as data from '../cms_export.json';

import Games from "./games.svelte";

$: active = 1;

const setActiveStudio = (id) => {
    active = id;

    let element = document.getElementById("gamesPanel");
    element.scrollIntoView({ behavior: "smooth"});
};

</script>

<style>

.studios {
    display: flex;
    flex-flow: row nowrap;
    justify-content: center;

    min-height: fit-content;
    max-height: 50vh;
}

.card {
    flex: 1 1 auto;
    margin: 1rem;
    border: 1px solid black;
}

.card[data-active="true"] {
    background-color: black;
    color: white;
}

.opaqueBg {
    background-color: white;
}

</style>