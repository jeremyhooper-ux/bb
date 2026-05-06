<script lang="ts">
  import Navigation from '$lib/components/Navigation.svelte';
  import HeroHeader from '$lib/components/HeroHeader.svelte';
  import FeaturedProjects from '$lib/components/FeaturedProjects.svelte';
  import HeadlineCTA from '$lib/components/HeadlineCTA.svelte';
  import Banner from '$lib/components/Banner.svelte';
  import Footer from '$lib/components/Footer.svelte';
</script>

<svelte:head>
  <title>Bakken & Bæck — Design & Technology Studio</title>
  <meta name="description" content="Bakken & Bæck is a design and technology studio. We build digital products, from zero to launch." />
</svelte:head>

<div class="page">
  <Navigation />
  <main>
    <HeroHeader />
    <FeaturedProjects />
    <HeadlineCTA />
    <Banner />
  </main>
  <Footer />
</div>

<style>
  .page {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
  }

  main {
    flex: 1;
  }
</style>
