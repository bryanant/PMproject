<footer class="content gradientBg">
    <div class="footerContent">
        <h3>{data.title}</h3>
        <p>Footer Links and shiz go here</p>
        <p>Yo! Dat Social Media Bizness</p>
        <p >Obligatory © {year} copyright notice goes here, all rights reserved.  You wouldn't steal a car.</p>
    </div>
</footer>

<script>

import * as data from '../cms_export.json';

const date = new Date();
const year = date.getFullYear();

</script>

<style>
.gradientBg {
    display: flex;
    flex-flow: column nowrap;

    background: linear-gradient(to bottom, transparent, transparent 40%, white 65%);

    min-height: 15rem;
    height: auto;
}

.footerContent {
    padding: 2rem;
    background-color: white;
    min-width: 1200px;
}

</style>