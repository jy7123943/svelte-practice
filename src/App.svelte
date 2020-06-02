<script>
	let people = [
		{ name: 'juno', hairColor: 'brown', age: 25, id: 1 },
		{ name: 'mario', hairColor: 'black', age: 45, id: 2 },
		{ name: 'lily', hairColor: 'pink', age: 35, id: 3 },
	];
</script>

<main>
	{#each people as person}
		<div>
			<h4>{person.name}</h4>
			<p>{person.age} years old, {person.hairColor} hair</p>
		</div>
	{/each}
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>
