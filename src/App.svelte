<!-- <script>
  // components
  import User from "./User.svelte";

  // variables
  const DATA_URL =
    "https://geektrust.s3-ap-southeast-1.amazonaws.com/adminui-problem/members.json";

  let response = [];

  // fetching de datos

  $: {
    getFetchingData();
  }

  // utils

  function getFetchingData() {
    fetch(DATA_URL)
      .then((res) => res.json())
      .then((data) => {
        console.log(data);
        response = data;
      })
      .catch((error) => console.log(error.message));
  }
</script>

<main>
  {#if response.length > 0}
    <strong>Tenemos {response.length} usuarios</strong>
    <div class="list-users">
      {#each response as { name, role }}
        <User {name} {role} />
      {/each}
    </div>
  {:else}
    <strong>No tenemos resultados</strong>
  {/if}
</main>

<style>
  main {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .list-users {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    justify-content: space-evenly;
    align-items: center;
  }
</style> -->
<script>
  // components
  import SearchBar from "./SearchBar.svelte";

  // variables
  const DATA_URL =
    "https://geektrust.s3-ap-southeast-1.amazonaws.com/adminui-problem/members.json";

  let response = [];

  // fetching de datos

  $: {
    getFetchingData();
  }

  // utils

  function getFetchingData() {
    fetch(DATA_URL)
      .then((res) => res.json())
      .then((data) => {
        console.log(data);
        response = data;
      })
      .catch((error) => console.log(error.message));
  }
</script>

<main>
  <SearchBar {response} />
</main>

<style>
  main {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }
</style>
