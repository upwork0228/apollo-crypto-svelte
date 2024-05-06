<script>
  import Button from '../../components/button.svelte'
  import { useNavigate } from 'svelte-navigator'

  const navigate = useNavigate()
</script>

<div class="title-container">
  <h1>Why go to the moon when we can go further</h1>
  <h2>
    We provides a fundamental analysis of the crypto market. In addition to
    tracking price, volume and market capitalisation.
  </h2>
  <div class="btn">
    <Button onclick={() => navigate('/coins')}>Go to the coins</Button>
  </div>
</div>

<style>
  .title-container {
    align-self: center;
  }
  .title-container h1 {
    font-size: 3rem;
  }

  .title-container h2 {
    padding: 1rem 0;
    font-size: 1.2rem;
    font-weight: 200;
    color: rgb(160, 160, 160);
  }

  .btn {
    position: relative;
    width: fit-content;
    margin-top: 1rem;
  }
</style>
