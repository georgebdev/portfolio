<script>
	import { Card, Button, ButtonGroup, Toast, Avatar } from 'flowbite-svelte';
	import Icon from '@iconify/svelte';
	import github from '$lib/images/github-mark.svg';
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
			It is currently {date.getHours()}:{date.getMinutes() < 10
				? '0' + date.getMinutes()
				: date.getMinutes()} &bull; {date.getDate()}/{date.getMonth() + 1}/{date.getFullYear()}
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
		<Card horizontal>
			<h1>About Me</h1>
			<p>
				Lorem ipsum, dolor sit amet consectetur adipisicing elit. Cupiditate sint sunt nobis, non,
				unde veritatis ab maiores, pariatur recusandae officia possimus voluptatum neque assumenda
				ullam suscipit! Quod quaerat ratione repudiandae!
			</p>
		</Card>
	{/if}

	{#if current == 'work'}
		<Card horizontal>
			<h1 class="text-3xl font-semibold">Past Work</h1>
			<p>See some other projects:</p>
			<ul class="list-disc dark:text-gray-400">
				<li class="ml-5">
					<a href="/">Testing</a>
				</li>
				<li class="ml-5">
					<a href="/">Testing</a>
				</li>
				<li class="ml-5">
					<a href="/">Testing</a>
				</li>
			</ul>
		</Card>
	{/if}

	{#if current == 'contact'}
		<Card horizontal>
			<h1 class="text-3xl font-semibold">Contact Me</h1>
			<p>
				Lorem ipsum, dolor sit amet consectetur adipisicing elit. Cupiditate sint sunt nobis, non,
				unde veritatis ab maiores, pariatur recusandae officia possimus voluptatum neque assumenda
				ullam suscipit! Quod quaerat ratione repudiandae!
			</p>
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
