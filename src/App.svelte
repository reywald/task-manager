<script>
  import ToDoInputForm from "./ToDoInputForm.svelte";
  import ToDoList from "./ToDoList.svelte";
  let nameEntered = false;

  let firstName = "Alice";
  let lastName = "Watson";

  $: fullName = firstName + " " + lastName;
</script>

<main>
  {#if nameEntered}
    <h1>Welcome to task manager, {fullName}!</h1>
    <ToDoInputForm userName={fullName} />
    <ToDoList />
  {:else}
    <h1>Welcome to task manager!</h1>
    <h3>Please enter your name:</h3>
    <div>
      <input type="text" placeholder="First name" required="required" />
    </div>
    <div>
      <input type="text" placeholder="Last name" required="required" />
    </div>
  {/if}
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }
</style>
