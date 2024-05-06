<script>
  import Nav from './nav.svelte'
  import ApolloLogo from './apolloLogo.svelte'

  let header
  let offset = 0

  window.addEventListener('scroll', (e) => {
    offset = window.scrollY
  })
</script>

<header class={offset > 20 && 'scroll-style'} bind:this={header}>
  <div class="col">
    <ApolloLogo />
    <Nav />
  </div>
</header>

<style>
  header {
    display: flex;
    justify-content: center;

    width: 100%;
    height: 90px;
    background: rgba(0, 0, 0, 0);
    backdrop-filter: blur(10px);
    position: fixed;
    top: 0;
    z-index: 999;
    transition: 0.3s;
  }

  header.scroll-style {
    height: 70px;
    background: rgba(0, 0, 0, 0.7);
  }

  .col {
    display: grid;
    grid-template-columns: auto 1fr;
    padding: 1rem;
    width: 100%;
    max-width: 1200px;
  }
</style>
