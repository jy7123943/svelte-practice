<script>
  let name;
  let hairColor;
  let age;
  // let fighting = false;
  // let sneaking = false;
  // let running = false;
  let skills = [];

  const handleSubmit = () => {
    console.log(name, hairColor, age, skills);
  };
</script>

<h3>Add a new person</h3>
<form on:submit|preventDefault={handleSubmit}>
  <input type="text" placeholder="name" bind:value={name} />
  <input type="text" placeholder="hair color" bind:value={hairColor} />
  <input type="number" placeholder="age" bind:value={age} />
  <h4>Skills:</h4>
  <!-- <label>
    <input type="checkbox" bind:checked={fighting} />fighting<br />
  </label>
  <label>
    <input type="checkbox" bind:checked={sneaking} />sneaking<br />
  </label>
  <label>
    <input type="checkbox"  bind:checked={running}/>running<br />
  </label> -->
  <label>
    <input type="checkbox" bind:group={skills} value="fighting" />fighting<br />
  </label>
  <label>
    <input type="checkbox" bind:group={skills} value="sneaking" />sneaking<br />
  </label>
  <label>
    <input type="checkbox" bind:group={skills} value="running" />running<br />
  </label>
  <button>Add Person</button>
</form>

<style></style>
