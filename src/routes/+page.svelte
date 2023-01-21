<script>
	const date = new Date();
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte app" />
</svelte:head>

<section> 	
	<h1 class="text-teal-700">
		{ "Good " + (date.getHours() < 12 ? "Morning" : (date.getHours() < 17 ? "Afternoon" : "Evening")) }
	</h1>
	<hr />
	<h3 class="text-teal-800 font-semibold">It is currently { date.getHours() }:{ date.getMinutes() } &bull; { date.getDate() }/{ date.getMonth() + 1 }/{ date.getFullYear() }</h3>
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 0.6;
	}

	h1 {
		width: 100%;
	}
</style>
