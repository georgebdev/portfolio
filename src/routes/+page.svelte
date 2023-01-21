<script>
	import { Card, Button, ButtonGroup, Toast, Avatar } from 'flowbite-svelte';
	import Icon from '@iconify/svelte';
	import github from '$lib/images/github-mark.svg'
	import { stagger } from '../animations';
	const date = new Date();
	let current = 'about';
	
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte app" />
</svelte:head>

<section>
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
				on:click={() => {
					current = 'about';
				}}
			>
				<Icon icon="mdi:home" height="auto" /> About Me
			</Button>
			<Button
				on:click={() => {
					current = 'work';
				}}
			>
				<Icon icon="mdi:book" height="auto" />
				Past Work
			</Button>
			<Button
				on:click={() => {
					current = 'contact';
				}}
			>
				<Icon icon="mdi:bullhorn" height="auto" />
				Contact
			</Button>
		</ButtonGroup>
		<br />
		<hr />
		<br />
		<div class="self-center">
			<Avatar size="sm" src={github} href="https://github.com/georgebdev" />
		</div>
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
