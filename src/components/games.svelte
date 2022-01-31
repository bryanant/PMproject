<section class="gamesContainer" data-active="{active}">
    <h3 class="studioName" id="gamesTitle">{studioInfo.name}'s Games (select):</h3>

    <div class="gamesAccordion"  style="{gameCountProp}">
        {#each games as game, i (game.id)}
            <article
                class="game"
                style="{backgroundImage(game.img)}"
                data-expanded="{activePanel === i}"
                data-collapsed="{activePanel !== i && activePanel >= 0}"
                on:click="{() => setActivePanel(i)}"
            >
                <h3 class="gameTitle">{game.name}</h3>
                {#if activePanel === i}
                    <div class="gameDeets">
                        <p>{game.content}</p>
                        <button class="buttonStyle">Go To Game Website</button>
                    </div>

                {/if}
            </article>
        {/each}

        {#if activePanel > -1}
        <button class="closePanel buttonStyle" on:click="{() => resetPanels()}">Back</button>
        {/if}
    </div>
</section>

<script>
import * as data from '../cms_export.json';

export let active;
export let studio;

const studioInfo = data.studios.find((studios) => studios.id === studio);

const games = data.games.filter((game) => game.studio === studioInfo.id);

const setActivePanel = (panel) => {
    activePanel = panel;

    let element = document.getElementById("gamesTitle");
    element.scrollIntoView({ behavior: "smooth"});
};

const resetPanels = () => activePanel = -1;

let activePanel = -1;

$: gameCountProp = `--gameCount:${games.length};`;

const backgroundImage = (path) => `--backgroundImage: url('${path}');`;

</script>

<style>

.gamesContainer {
    background-color: white;

    width: 100%;
    height: 100%;
    min-height: 100vh;
}

.gamesContainer[data-active="false"] {
    display: none;
}
.gamesContainer[data-active="true"] {
    display: block;
}

.studioName {
    text-align: center;
}

.gamesAccordion {
    position: relative;

    display: flex;
    flex-flow: row nowrap;
    justify-content: space-around;
    align-items: flex-start;

    margin: 2rem;

    height: 100%;
}

.game {
    display: flex;
    flex-flow: column nowrap;
    align-items: flex-start;
    justify-content: center;

    height: calc(100% - 8rem);
    width: calc(80% / var(--gameCount));

    background-image: var(--backgroundImage);
    background-position: fixed;
    background-size: cover;
    background-repeat: no-repeat;

    backface-visibility: hidden;
    transform: translate3d(0);

    cursor: pointer;

    transition: width 0.2s ease-in-out;
}

.game:hover {
    width: calc(100% / var(--gameCount));
}

.game[data-expanded="true"] {
    width: 100%;
}

.game[data-collapsed="true"] {
    width: 0%;

    opacity: 0;
}

.gameTitle {
    width: fit-content;
    padding: 2rem;
    background-color: white;
}

.gameDeets {
    width: 25vw;
    padding: 4rem;
    background-color: rgba(255, 255, 255, 0.75);

    opacity: 0;
    transform: translateX(-101%);

    transition: all 500ms ease-in-out;
}

[data-expanded="true"] .gameDeets {
    opacity: 1;
    transform: translateX(0);
}

.closePanel {
    position: absolute;

    top: 4rem;
    right: 4rem;
}

</style>