<script>
  // variables
  export let name, role;

  // events
  const handleClick = () => {
    const text = `Name: ${name}, role: ${role}`;
    console.log("click me", text);
  };
</script>

<section class="user-item" on:mousedown={handleClick}>
  <p>{name}</p>
  <p>{role}</p>
</section>

<style>
  .user-item {
    display: flex;
    flex-direction: row;
    gap: 1rem;
    justify-content: space-between;
    align-items: center;
    padding: 0 1rem;
    color: white;
    border-radius: 10px;
    cursor: pointer;
    min-width: 200px;
    height: auto;
    background-color: rgb(38, 125, 125);
  }

  .user-item:hover {
    background-color: rgb(54, 166, 166);
  }
</style>
