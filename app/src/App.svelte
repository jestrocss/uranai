<script>
	import Button from "@smui/button";
	import { Router, Link, Route } from "svelte-routing";
	import Settings from "./Settings.svelte";
	import Main from "./Main.svelte";
</script>

<svelte:head>
	<link
		rel="stylesheet"
		href="https://cdn.jsdelivr.net/npm/svelte-material-ui/bare.min.css"
	/>
	<link
		rel="stylesheet"
		href="https://fonts.googleapis.com/icon?family=Material+Icons"
	/>
	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
	<link
		href="https://fonts.googleapis.com/css2?family=Kosugi+Maru&display=swap"
		rel="stylesheet"
	/>
</svelte:head>

<Router>
	<nav>
		<Link to="settings">
			<Button color="secondary">設定</Button>
		</Link>
		<Link to="">
			<Button color="secondary">メイン</Button>
		</Link>
	</nav>
	<main>
		<Route path="">
			<Main />
		</Route>
		<Route path="settings">
			<Settings />
		</Route>
	</main>
</Router>

<style>
	* {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
		font-family: "Kosugi Maru", sans-serif;
	}

	:global(html, body) {
		margin: 0;
		padding: 0;
		font-size: 16px;
		background-color: #fafafa;
	}

	main {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		gap: 20px;
		min-height: 100vh;
	}
</style>
