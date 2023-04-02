<script>
  // components
  import ListUser from "./ListUser.svelte";
  
  // variables
  export let response = [];
  let name = "";

  $: filtered = response;

  // events
  const handleSubmit = (e) => {
    e.preventDefault();
    console.log(name);

    filtered = response.filter((e) =>
      e.name.toLowerCase().includes(name.toLowerCase())
    );

    name = "";
  };
</script>

<div class="container">
  <div class="search-user-bar">
    <form class="form-user" on:submit={handleSubmit}>
      <input type="text" placeholder="Enter name..." bind:value={name} />
      <button type="submit">Submit</button>
    </form>
  </div>
  <ListUser array={filtered} />
</div>

<style>
  .container {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .search-user-bar {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .form-user {
    display: flex;
    gap: 1rem;
  }
</style>
