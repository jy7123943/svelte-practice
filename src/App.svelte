<script>
	import Modal from './Modal.svelte';

	let showModal = false;

	const toggleModal = () => {
		showModal = !showModal;
	};

	let people = [
		{ name: 'juno', hairColor: 'brown', age: 25, id: 1 },
		{ name: 'mario', hairColor: 'black', age: 45, id: 2 },
		{ name: 'lily', hairColor: 'pink', age: 35, id: 3 },
	];

	const handleClick = (id) => {
		// delete the person from people
		people = people.filter(person => person.id !== id);
	}

	let textColor = 'blue';
	const handleAnchor = () => {
		textColor = textColor === 'blue' ? 'red' : 'blue';
	}

	let num = 3;
</script>

<Modal {showModal} on:click={toggleModal}>
	<h3>Add a new person</h3>
	<form>
		<input type="text" placeholder="name" />
		<input type="text" placeholder="hair color" />
		<button>Add Person</button>
	</form>
	<!-- <div slot="title">
		<h3>Add a new person</h3>
	</div> -->
</Modal>
<main>
	<button on:click={toggleModal}>Open Modal</button>
	<a href='https://www.google.com' on:click|preventDefault={handleAnchor} style='color: {textColor}'>helloworld</a>
	<!-- dom manipulating을 잘 하기 위해 person.id와 같이 특정 id를 key값으로 넣어줌으로써 people array data와 DOM을 연결함 -->
	{#each people as person (person.id)}
		<div>
			<h4>{person.name}</h4>
			{#if person.hairColor === 'black'}
				<p><strong>MASTER NINJA</strong></p>
			{/if}
			<p>{person.age} years old, {person.hairColor} hair</p>
			<button on:click={() => handleClick(person.id)}>delete</button>
		</div>
	{:else}
		<p>There are no people to show...</p>
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
