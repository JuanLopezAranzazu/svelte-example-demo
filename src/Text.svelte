<script>
  export let initialName = "svelte";
  export let changeName = "world";

  let text = initialName;

  const handleClick = () => {
    console.log("click me");
    text = text === initialName ? changeName : initialName;
  };

  $: colorText = text === initialName ? "#135a38" : "#1c247a";

</script>

<main>
  <h1 style="color: {colorText};">Hello {text}!</h1>
  <button type="button" on:click={handleClick}>Click me</button>
</main>

<style>
  main {
    display: flex;
    flex-direction: row;
    gap: 1rem;
  }
</style>
