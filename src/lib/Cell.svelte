<script>
  export let content = "";
  export let locked = false;

  function incrementContent() {
    if (locked) {
      return;
    }

    const newValue = Number(content) + 1;
    if (newValue === 10) {
      content = "";
    } else {
      // @ts-ignore
      content = Number(content) + 1;
    }
  }
</script>

<div class="cell" class:locked on:click={incrementContent}>
  {content}
</div>

<style>
  .cell {
    text-align: center;
    border: 1px solid grey;
    border-radius: 0px;

    box-sizing: border-box;
    width: 3em;
    height: 3em;
    padding-top: 1em;

    margin: 0px;
  }

  .locked {
    background-color: lightgray;
  }
</style>
