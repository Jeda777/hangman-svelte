<script>
  export let handleKey;
  export let checked = [];
  export let ended;
  const keys = [
    "a",
    "b",
    "c",
    "d",
    "e",
    "f",
    "g",
    "h",
    "i",
    "j",
    "k",
    "l",
    "m",
    "n",
    "o",
    "p",
    "q",
    "r",
    "s",
    "t",
    "u",
    "v",
    "w",
    "x",
    "y",
    "z",
  ];
</script>

<div class="keyboard">
  {#each keys as key}
    <button
      disabled={checked.includes(key) ? true : ended ? true : false}
      {key}
      class={checked.includes(key) ? "used" : ended ? "used" : ""}
      on:click={() => handleKey(key)}>{key}</button
    >
  {/each}
</div>

<style lang="scss">
  .keyboard {
    display: flex;
    flex-wrap: wrap;
    max-width: 500px;
    gap: 0.125rem;
    justify-content: center;
    margin-bottom: 2rem;
    button {
      width: 40px;
      height: 40px;
      border: 2px solid black;
      display: flex;
      justify-content: center;
      align-items: center;
      text-transform: uppercase;
      cursor: pointer;
      transition: all 0.3s ease-in-out;
      &:hover {
        background: rgba(0, 0, 0, 0.2);
      }
      &.used {
        background: rgba(0, 0, 0, 0.5);
        cursor: default;
        &:hover {
          background: rgba(0, 0, 0, 0.5);
        }
      }
    }
  }
</style>
