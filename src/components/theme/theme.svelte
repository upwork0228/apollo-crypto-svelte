<script>
  import Header from '../header/header.svelte'
</script>

<div class="theme">
  <Header />
  <slot />
</div>

<style>
  :global(body, *) {
    margin: 0;
    padding: 0;
    color: white;
  }

  :global(body) {
    width: 100%;
    background: #080808;
  }

  :global(li) {
    list-style: none;
  }

  .theme {
    width: 100%;
    min-height: 100vh;
    background: rgba(2, 7, 16);
  }
</style>
