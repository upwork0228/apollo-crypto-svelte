<script>
  import { link, useLocation, useNavigate } from 'svelte-navigator'
  import Cover from './sections/cover.svelte'

  export const location = useLocation()
  export const navigate = useNavigate()
</script>

<Cover />
<div class="a" />

<style>
  .a {
    width: 100%;
    height: 500px;
  }
</style>
