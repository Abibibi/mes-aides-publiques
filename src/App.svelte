<script>
	import { onMount } from 'svelte';
	import axios from 'axios';
	import truncate from 'lodash.truncate';

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
	{#each supportOptions as { nature, picture, title, description }}
		<Card
			type={nature.title}
			picture={picture}
			title={title}
			description={truncate(description, { length: 165, separator: /,?\.* +/})}
		/>
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

	@media only screen and (min-width: 550px) {
		main {
			display: grid;
			grid-template-columns: 1fr 1fr;
			gap: 1rem;
		}
	}

	@media only screen and (min-width: 768px) {
		main {
			grid-template-columns: 1fr 1fr 1fr;
		}
	}

	@media only screen and (min-width: 1024px) {
		main {
			grid-template-columns: 1fr 1fr 1fr 1fr;
		}
	}
</style>