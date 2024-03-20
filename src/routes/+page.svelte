<script lang="ts">
	import { faker } from '@faker-js/faker';

	const randomName = () => {
		const randomAnimal = faker.animal.type();
		const randomPreposition = faker.word.preposition();
		const randomObject = faker.word.noun();

		return `${randomAnimal} ${randomPreposition} the ${randomObject}`;
	};

	let name = '';
</script>

<div class="column-layout">
	<main class="pt-12">
		<h1>Old Time Name Generator</h1>
		<p>{name}</p>
		<button on:click={() => (name = randomName())}>Randomize</button>
	</main>
</div>

<style>
	.column-layout {
		display: grid;
		grid-template-columns: 1fr min(900px, 100%) 1fr;
	}

	.column-layout > * {
		grid-column: 2;
	}
</style>
