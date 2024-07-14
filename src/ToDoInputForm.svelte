<script>
  import { toDoItems } from "./store.js";
  export let userName;
  let newItem = "";

  function addToList() {
    $toDoItems = [...$toDoItems, { text: newItem, status: false }];
    newItem = "";
  }
</script>

<input bind:value={newItem} type="text" placeholder="Add a new task" />
<button on:click={addToList}>Add</button>

<h3>{userName}'s task list:</h3>
