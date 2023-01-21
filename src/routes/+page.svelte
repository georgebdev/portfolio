<script>
	import { Card, Button, ButtonGroup, Toast } from 'flowbite-svelte';
	import Icon from '@iconify/svelte';
	import github from '$lib/images/github-mark.svg'
	const date = new Date();
	let current = 'about';
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte app" />
</svelte:head>

<section>
	<Toast>
		<svelte:fragment slot="icon">
			<!-- <svg
				xmlns="http://www.w3.org/2000/svg"
				fill="none"
				viewBox="0 0 24 24"
				stroke-width="1.5"
				stroke="currentColor"
				class="w-6 h-6"
				><path
					stroke-linecap="round"
					stroke-linejoin="round"
					d="M15.362 5.214A8.252 8.252 0 0112 21 8.25 8.25 0 016.038 7.048 8.287 8.287 0 009 9.6a8.983 8.983 0 013.361-6.867 8.21 8.21 0 003 2.48z"
				/><path
					stroke-linecap="round"
					stroke-linejoin="round"
					d="M12 18a3.75 3.75 0 00.495-7.467 5.99 5.99 0 00-1.925 3.546 5.974 5.974 0 01-2.133-1A3.75 3.75 0 0012 18z"
				/>
			</svg> -->
			<img src={github} alt="a"/>
		</svelte:fragment>
		<a href="https://github.com/georgebdev">Click here to view my GitHub</a>
	</Toast>
	<br />
	<Card>
		<h1 class="text-teal-700">
			{'Good ' +
				(date.getHours() < 12 ? 'Morning' : date.getHours() < 17 ? 'Afternoon' : 'Evening')}
		</h1>
		<br />
		<h3 class="text-teal-800 font-semibold self-center">
			It is currently {date.getHours()}:{date.getMinutes()} &bull; {date.getDate()}/{date.getMonth() +
				1}/{date.getFullYear()}
		</h3>
		<br />
		<ButtonGroup>
			<Button
				shadow="teal"
				on:click={() => {
					current = 'about';
				}}
			>
				<Icon icon="mdi:home" height="auto" /> About Me
			</Button>
			<Button
				shadow="teal"
				on:click={() => {
					current = 'work';
				}}
			>
				<Icon icon="mdi:book" height="auto" />
				Past Work
			</Button>
			<Button
				shadow="teal"
				on:click={() => {
					current = 'contact';
				}}
			>
				<Icon icon="mdi:bullhorn" height="auto" />
				Contact
			</Button>
		</ButtonGroup>
	</Card>

	<br />

	{#if current == 'about'}
		<Card>
			<h1 class="text-3xl font-semibold">About</h1>
			<p class="text-lg self-center">Testing</p>
		</Card>
	{/if}

	{#if current == 'work'}
		<Card>
			<h1 class="text-3xl font-semibold">Work</h1>
		</Card>
	{/if}

	{#if current == 'contact'}
		<Card>
			<h1 class="text-3xl font-semibold">Contact</h1>
		</Card>
	{/if}
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
