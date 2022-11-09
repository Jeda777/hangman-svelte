<script>
  export let checked = [];
  export let arr;
  export let ended;
</script>

<div class="sentence">
  {#each arr as letter}
    {#if letter !== " "}
      <div
        class={`letter ${checked.includes(letter) ? "active" : ""} ${
          !checked.includes(letter) && ended ? "missed" : ""
        }`}
      >
        {letter}
      </div>
    {/if}
    {#if letter === " "}
      <div class="space" />
    {/if}
  {/each}
</div>

<style lang="scss">
  .sentence {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    margin-bottom: 1rem;
    text-transform: uppercase;
    div {
      height: 30px;
      width: 20px;
      border-bottom: 2px solid black;
      display: flex;
      justify-content: center;
      font-size: 0px;
      &.space {
        border: none;
      }
      &.active {
        font-size: 24px !important;
      }
      &.missed {
        font-size: 24px !important;
        color: red;
      }
    }
  }
</style>
