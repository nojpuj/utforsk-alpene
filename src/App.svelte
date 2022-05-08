<script>
	import Main from "./komponenter/main.svelte";
	import Destinasjoner from "./komponenter/destinasjoner.svelte";
	import Aktiviteter from "./komponenter/aktiviteter.svelte";
	import Steder from "./komponenter/stederåbo.svelte";
	import KontaktOss from "./komponenter/kontaktoss.svelte";

	let visning;

	function sidevisning(side) {
		visning = side;
	}

</script>

<main>
	<div class="header-box"><h1 class="header" on:click="{() => sidevisning('Main')}">Utforsk Alpene</h1></div>
		<ul class="navbar">
			<li class="nav-item2" on:click="{() => sidevisning('Main')}"><img id="logo" src="icon.png" alt="logo"></li>
			<li class="nav-item" on:click="{() => sidevisning('Destinasjoner')}">Destinasjoner</li>
			<li class="nav-item" on:click="{() => sidevisning('Aktiviteter')}">Aktiviteter</li>
			<li class="nav-item" on:click="{() => sidevisning('Steder')}">Steder å bo</li>
			<li class="nav-item" on:click="{() => sidevisning('KontaktOss')}">Kontakt oss</li>
		</ul>
	{#if visning === 'Destinasjoner'}
		<Destinasjoner />
	{:else if visning === 'Aktiviteter'}
		<Aktiviteter />
	{:else if visning === 'Steder'}
		<Steder />
	{:else if visning === 'KontaktOss'}
		<KontaktOss />
	{:else}
		<Main />
	{/if}
</main>

<style>

	* {
		font-family: 'Nunito', sans-serif;
	}

	main {
		text-rendering: optimizeLegibility;
		scroll-behavior: smooth;
	}

	.header-box {
		cursor: pointer;
		display: flex;
		justify-content: center;
	}

	.navbar {
		display: flex;
		justify-content: center;
		list-style-type: none;
		width: 100%;
		margin: 0;
		padding: 0;
		overflow: hidden;
		position: sticky;
		top: 0;
		z-index: 999;
		border: 1px solid #808080;
		border-right: none;
		border-left: none;
		background-color: #fff;
	}

	.nav-item {
		cursor: pointer;
		text-decoration: none;
		color: #000000;
		text-align: center;
		display: block;
		padding: 14px 26px;
	}

	.nav-item2 {
		cursor: pointer;
		display: block;
	}

	.header {
		font-size: 3rem;
	}

	#logo {
		position: relative;
		width: 40px;
		height: 40px;
	}

	li:hover {
		color: orange;
	}

	.header:hover {
		color: orange;
	}

</style>