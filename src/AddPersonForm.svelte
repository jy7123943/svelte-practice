<script>
  let name;
  let hairColor;
  let age;

  const handleSubmit = () => {
    console.log(name, hairColor, age);
  };
</script>

<h3>Add a new person</h3>
<form on:submit|preventDefault={handleSubmit}>
  <input type="text" placeholder="name" bind:value={name} />
  <input type="text" placeholder="hair color" bind:value={hairColor} />
  <input type="number" placeholder="age" bind:value={age} />
  <button>Add Person</button>
</form>

<style></style>
