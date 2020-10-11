<script>
	import { onMount } from 'svelte';
	import axios from 'axios';

	import Card from './Card.svelte';

	let supportOptions = [];

	let supportError;

	onMount(async () => {

		try {
			const { data: { aides } } = await axios.get('https://cors-anywhere.herokuapp.com/https://dev.api.mesaidespubliques.fr/Aides/all?page=1&count=50');

			supportOptions = aides;
		}
		catch (error) {
			supportError = error;
		}
	});
</script>

<main>
	{#each supportOptions as option}
		<Card { ...option } />
	{/each}
</main>

<style>
	main {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: .5rem;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>