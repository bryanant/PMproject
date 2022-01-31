<Nav></Nav>

<main class="parallax">
	<div class="background parallaxBg">
		<img src="https://placeimg.com/1920/1080/arch" />
		<div class="spacer"/>
		<img src="https://placeimg.com/1920/1080/people" />
	</div>

	<div class="foreground">
		<Hero title={data.title} tagline={data.tagline}/>
	</div>

	<div class="foreground">
	<Studios></Studios>
	</div>

	<div class="foreground">
	<News></News>
	</div>

	<div class="parallaxLayer foreground">
	<Footer></Footer>
	</div>
</main>


<!-- at the end, write up of unfinished points, potential issues that may arise, further research items, tasks that need to be completed / outstanding unknowns that weren't covered initially -->

<script>
	import * as data from './cms_export.json';

	import Hero from "./components/hero.svelte";
	import Footer from "./components/footer.svelte";
	import Nav from "./components/nav.svelte";
	import News from "./components/news.svelte";
	import Studios from "./components/studios.svelte";
</script>

<style>
.parallax {
	perspective: 1px;
	height: 100vh;
	overflow-x: hidden;
	overflow-y: auto;
}

.parallaxBg {
	position: absolute;
	inset: 0;

	height: 80%;

	display: flex;
	flex-flow: column nowrap;
	justify-content: space-between;
}

.foreground {
	position: relative;
	width: 100%;
	transform: translateZ(0);
}

.background {
	transform: translateZ(-1px) scale(2.25);
}

.spacer {
	display: block;
	height: 50vh;
	background: transparent;
}

</style>