<script lang="ts">
  let { mediaUrl = '' }: { mediaUrl?: string } = $props();
</script>

<section class="hero">
  <div class="hero-media">
    {#if mediaUrl}
      <img src={mediaUrl} alt="Hero" class="hero-image" />
    {:else}
      <div class="hero-placeholder" aria-hidden="true"></div>
    {/if}
  </div>
  <div class="hero-text container">
    <p class="heading-lg hero-copy">
      <span class="secondary">Bakken &amp; Bæck</span> is a design and technology studio. We build digital products, from zero to launch.
    </p>
  </div>
</section>

<style>
  .hero {
    display: flex;
    flex-direction: column;
    width: 100%;
    background: var(--surface-background-primary);
  }
  .hero-media {
    width: 100%;
    height: 80vh;
    overflow: hidden;
    position: relative;
    background: var(--colour-grey-200);
  }
  .hero-image,
  .hero-placeholder {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
  .hero-placeholder {
    background: var(--colour-grey-200);
  }
  .hero-text {
    display: flex;
    align-items: center;
    justify-content: center;
    padding-top: var(--grid-margin);
    padding-bottom: var(--spacing-module-padding-md);
  }
  .hero-copy {
    flex: 1;
    color: var(--text-default-primary);
  }
  .secondary {
    color: var(--text-default-secondary);
  }
</style>
