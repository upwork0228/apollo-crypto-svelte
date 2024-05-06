<script>
  import { Router, Route } from 'svelte-navigator'
  import Theme from './components/theme/theme.svelte'
  import Home from './screens/Home.svelte'
  import Coins from './screens/Coins.svelte'
</script>

<Router url="localhost:8080">
  <Theme>
    <Route path="coins" component={Coins} />
    <Route path="/" component={Home} />
  </Theme>
</Router>

<style>
</style>
