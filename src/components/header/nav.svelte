<script>
  import { link, useLocation } from 'svelte-navigator'

  let location = useLocation()
  let selected
  let barPosition = 0

  const setBarPosition = (e, action) => {
    if (action === 'enter') {
      barPosition = `${e.target.children[0].offsetLeft}px`
    } else if (action === 'leave') {
      barPosition = `${selected?.children[0].offsetLeft}px`
    }
  }

  $: barPosition = `${selected?.children[0].offsetLeft}px`

  const links = [
    {
      pathname: '/',
      name: 'Home',
    },
    {
      pathname: '/coins',
      name: 'Coins',
    },
    {
      pathname: '/coins/recently',
      name: 'Recently Added',
    },
    {
      pathname: '/coins/trending',
      name: 'Large Movers',
    },
    {
      pathname: '/coins/categories',
      name: 'Categories',
    },
  ]
</script>

<nav>
  <ul>
    {#each links as { pathname, name }}
      {#if $location.pathname === pathname}
        <li
          bind:this={selected}
          class="selected"
          on:mouseleave={(e) => setBarPosition(e, 'leave')}
          on:mouseenter={(e) => setBarPosition(e, 'enter')}
        >
          <a href={pathname} use:link>{name}</a>
        </li>
      {:else}
        <li
          on:mouseleave={(e) => setBarPosition(e, 'leave')}
          on:mouseenter={(e) => setBarPosition(e, 'enter')}
        >
          <a href={pathname} use:link>{name}</a>
        </li>
      {/if}
    {/each}
  </ul>
  <div class="bar" style="--position: {barPosition}" />
</nav>

<style>
  nav {
    align-self: center;
    justify-self: flex-end;
    position: relative;
  }

  ul {
    display: flex;
  }

  li {
    display: grid;
    justify-content: center;
    padding: 0 0.75rem;
  }

  .bar {
    position: absolute;
    bottom: -10px;
    width: 20px;
    height: 2px;
    background-color: rgb(0, 255, 157);
    transition: 0.3s;
    left: var(--position);
    filter: drop-shadow(0px 0px 3px rgb(0, 255, 157, 1));
  }

  a {
    color: white;
    text-decoration: none;
  }
</style>
