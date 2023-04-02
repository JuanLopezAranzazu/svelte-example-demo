<script>
  // components
  import User from "./User.svelte";

  // variables
  export let array = [];
</script>

<div class="list-users">
  {#if array.length > 0}
    {#each array as { name, role }}
      <User {name} {role} />
    {/each}
  {:else}
    <strong>No hay resultados</strong>
  {/if}
</div>

<style>
  .list-users {
    display: flex;
    gap: 1rem;
    justify-content: center;
    align-items: center;
  }

  @media screen and (min-width: 768px) {
    .list-users {
      flex-direction: row;
      flex-wrap: wrap;
    }
  }

  @media screen and (max-width: 767px) {
    .list-users {
      display: flex;
      flex-direction: column;
    }
  }
</style>
