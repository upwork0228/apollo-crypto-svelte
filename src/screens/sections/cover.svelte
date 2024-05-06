<script>
  import CoverTitleSection from './coverTitleSection.svelte'
  import CoverTopCoins from './coverTopCoins.svelte'
</script>

<section class="bg">
  <div class="glass" />
  <img
    src="https://png.pngtree.com/background/20210709/original/pngtree-colorful-background-picture-image_507712.jpg"
    alt="background pngtree.com"
  />
  <section class="cover">
    <CoverTitleSection />
    <CoverTopCoins />
  </section>
</section>

<style>
  /* background */
  .bg {
    display: flex;
    justify-content: center;
    padding-top: 102px;
    position: relative;
    top: 0;
    width: 100%;
  }

  img {
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0;
    left: 0;
    z-index: 0;
    object-fit: cover;
    object-position: center;
  }

  .glass {
    width: 100%;
    height: 100%;
    background-color: rgba(2, 7, 16, 0.93);
    backdrop-filter: blur(50px);
    background: linear-gradient(
      0deg,
      rgba(2, 7, 16, 1) 0%,
      rgba(2, 7, 16, 0.93) 21%
    );
    position: absolute;
    top: 0;
    z-index: 1;
  }

  .cover {
    display: grid;
    grid-template-columns: 1fr 1fr;
    justify-items: center;
    gap: 1rem;

    position: relative;
    z-index: 10;
    width: 100%;
    max-width: 1200px;
    padding: 6rem 2rem;
    padding-top: 2rem;
  }
</style>
