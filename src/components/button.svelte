<script>
  export let onclick
</script>

<div class="button-container" on:click={onclick}>
  <div class="border-container">
    <div class="border-top" />
    <div class="border-bot" />
  </div>
  <button>
    <slot />
  </button>
</div>

<style>
  .button-container {
    position: relative;
    cursor: pointer;
  }

  .border-container {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    filter: drop-shadow(0px 0px 0px rgb(0, 255, 157, 1));
    transition: 0.3s;
  }
  .button-container:hover .border-container {
    filter: drop-shadow(0px 0px 3px rgb(0, 255, 157, 1));
  }

  .button-container button {
    width: fit-content;
    padding: 1rem 2rem;
    margin: 0;
    background: none;
    border: none;
    color: rgb(160, 160, 160);
    transition: 0.3s;
  }

  .button-container:hover button {
    color: white;
  }

  .border-top,
  .border-bot {
    content: '';
    position: absolute;
    top: 0;
    right: 0;
    width: 100%;
    height: 100%;
    background: rgb(0, 255, 157);
  }

  .border-top {
    clip-path: polygon(
      100% 0,
      100% 3px,
      100% 50%,
      calc(100% - 3px) 50%,
      calc(100% - 3px) 3px,
      75% 3px,
      75% 0
    );
    transition: 0.3s;
  }

  .button-container:hover .border-top {
    clip-path: polygon(
      100% 0,
      100% 3px,
      100% 100%,
      calc(100% - 3px) 100%,
      calc(100% - 3px) 3px,
      0 3px,
      0 0
    );
  }

  .border-bot {
    clip-path: polygon(
      0 100%,
      25% 100%,
      25% calc(100% - 3px),
      3px calc(100% - 3px),
      3px 50%,
      0 50%
    );
    transition: 0.3s;
  }

  .button-container:hover .border-bot {
    clip-path: polygon(
      0 100%,
      100% 100%,
      100% calc(100% - 3px),
      3px calc(100% - 3px),
      3px 0,
      0 0
    );
  }
</style>
