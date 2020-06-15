<script>
  import { createEventDispatcher } from 'svelte';

  let dispatch = createEventDispatcher();

  let name;
  let hairColor;
  let age;
  let skills = [];

  const handleSubmit = () => {
    const person = {
      name,
      hairColor,
      age,
      skills,
      id: Math.random()
    };

    dispatch('addPerson', person);
  };
</script>

<h3>Add a new person</h3>
<form on:submit|preventDefault={handleSubmit}>
  <input type="text" placeholder="name" bind:value={name} />
  <input type="number" placeholder="age" bind:value={age} />
  <h4>Skills:</h4>
  <label>
    <input type="checkbox" bind:group={skills} value="fighting" />fighting<br />
  </label>
  <label>
    <input type="checkbox" bind:group={skills} value="sneaking" />sneaking<br />
  </label>
  <label>
    <input type="checkbox" bind:group={skills} value="running" />running<br />
  </label>
  <h4>hairColor:</h4>
  <select bind:value={hairColor}>
    <option value="black">black</option>
    <option value="orange">orange</option>
    <option value="brown">brown</option>
    <option value="silver">silver</option>
  </select>
  <button>Add Person</button>
</form>

<style></style>
