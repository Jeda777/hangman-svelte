<script>
  export let missCount;
  export let ended;
  export let win;
  export let handleReset;
</script>

<div id="man" class={`stage-${missCount}`}>
  <div class="part base" />
  <div class="part part1" />
  <div class="part part2" />
  <div class="part part3" />
  <div class="head" />
  <div class="body" />
  <div class="arm arm1" />
  <div class="arm arm2" />
  <div class="leg leg1" />
  <div class="leg leg2" />
  {#if ended}
    <div class="ending">
      <p>{win}</p>
      <button type="button" on:click={() => handleReset()}>Play again</button>
    </div>
  {/if}
</div>

<style lang="scss">
  #man {
    width: 220px;
    height: 400px;
    position: relative;
    div {
      position: absolute;
      transform: translate(-50%, -50%);
      background: black;
    }
    .base {
      height: 5px;
      width: 100px;
      bottom: 50px;
      left: 70px;
    }
    .part1 {
      height: 295px;
      width: 5px;
      left: 70px;
      top: 200px;
    }
    .part2 {
      height: 5px;
      width: 100px;
      top: 50px;
      left: 117px;
    }
    .part3 {
      height: 50px;
      width: 5px;
      left: 168px;
      top: 72px;
    }
    .head {
      width: 45px;
      height: 45px;
      border: 5px solid black;
      background: none !important;
      border-radius: 100%;
      left: 168px;
      top: 120px;
    }
    .body {
      width: 5px;
      height: 70px;
      left: 168px;
      top: 172px;
    }
    .arm {
      width: 5px;
      height: 50px;
      rotate: 35deg;
      top: 160px;
      left: 138px;
    }
    .arm2 {
      rotate: -35deg;
      top: 156px;
      left: 196px;
    }
    .leg {
      width: 5px;
      height: 50px;
      rotate: 35deg;
      top: 220px;
      left: 138px;
    }
    .leg2 {
      rotate: -35deg;
      top: 216px;
      left: 196px;
    }
    .ending {
      color: white;
      background: rgb(0 0 0 / 0.5);
      border-radius: 1rem;
      height: 100px;
      left: 50%;
      top: 50%;
      width: 200px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      gap: 0.5rem;
      p {
        font-size: 28px;
      }
      button {
        cursor: pointer;
        border: none;
        background: white;
        font-size: 16px;
        padding: 0.25rem 0.5rem;
        border-radius: 0.75rem;
        transition: all 0.3s ease-in-out;
        &:hover {
          opacity: 0.7;
        }
      }
    }
    &.stage-0 {
      .base {
        opacity: 0;
      }
      .part1 {
        opacity: 0;
      }
      .part2 {
        opacity: 0;
      }
      .part3 {
        opacity: 0;
      }
      .head {
        opacity: 0;
      }
      .body {
        opacity: 0;
      }
      .arm1 {
        opacity: 0;
      }
      .arm2 {
        opacity: 0;
      }
      .leg1 {
        opacity: 0;
      }
      .leg2 {
        opacity: 0;
      }
    }
    &.stage-1 {
      .part1 {
        opacity: 0;
      }
      .part2 {
        opacity: 0;
      }
      .part3 {
        opacity: 0;
      }
      .head {
        opacity: 0;
      }
      .body {
        opacity: 0;
      }
      .arm1 {
        opacity: 0;
      }
      .arm2 {
        opacity: 0;
      }
      .leg1 {
        opacity: 0;
      }
      .leg2 {
        opacity: 0;
      }
    }
    &.stage-2 {
      .part2 {
        opacity: 0;
      }
      .part3 {
        opacity: 0;
      }
      .head {
        opacity: 0;
      }
      .body {
        opacity: 0;
      }
      .arm1 {
        opacity: 0;
      }
      .arm2 {
        opacity: 0;
      }
      .leg1 {
        opacity: 0;
      }
      .leg2 {
        opacity: 0;
      }
    }
    &.stage-3 {
      .part3 {
        opacity: 0;
      }
      .head {
        opacity: 0;
      }
      .body {
        opacity: 0;
      }
      .arm1 {
        opacity: 0;
      }
      .arm2 {
        opacity: 0;
      }
      .leg1 {
        opacity: 0;
      }
      .leg2 {
        opacity: 0;
      }
    }
    &.stage-4 {
      .head {
        opacity: 0;
      }
      .body {
        opacity: 0;
      }
      .arm1 {
        opacity: 0;
      }
      .arm2 {
        opacity: 0;
      }
      .leg1 {
        opacity: 0;
      }
      .leg2 {
        opacity: 0;
      }
    }
    &.stage-5 {
      .body {
        opacity: 0;
      }
      .arm1 {
        opacity: 0;
      }
      .arm2 {
        opacity: 0;
      }
      .leg1 {
        opacity: 0;
      }
      .leg2 {
        opacity: 0;
      }
    }
    &.stage-6 {
      .arm1 {
        opacity: 0;
      }
      .arm2 {
        opacity: 0;
      }
      .leg1 {
        opacity: 0;
      }
      .leg2 {
        opacity: 0;
      }
    }
    &.stage-7 {
      .arm2 {
        opacity: 0;
      }
      .leg1 {
        opacity: 0;
      }
      .leg2 {
        opacity: 0;
      }
    }
    &.stage-8 {
      .leg1 {
        opacity: 0;
      }
      .leg2 {
        opacity: 0;
      }
    }
    &.stage-9 {
      .leg2 {
        opacity: 0;
      }
    }
    //&.stage-9 {}
  }
</style>
