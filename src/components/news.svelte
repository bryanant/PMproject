<section class="content opaqueBg">
    <div class="panelContent">
        <h2>News And Media</h2>

        Yo, this stuff is happening!

        {#each data.newsPosts as newsItem}
        <article class="newsPost">
            <h3>{newsItem.title}</h3>
            <summary>{newsItem.content}</summary>
        </article>
        {/each}
    </div>
</section>

<script>
import * as data from '../cms_export.json';
</script>

<style>
.opaqueBg {
    background-color: lightgray;

    height: fit-content;
}

.newsPost {
    padding: 2rem 0;
}

</style>