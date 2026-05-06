<script lang="ts">
  let {
    question = 'Want to work with us?',
    answer = "We'd love to hear from you!",
    ctaText = 'Get in touch',
    ctaHref = '/contact'
  }: {
    question?: string;
    answer?: string;
    ctaText?: string;
    ctaHref?: string;
  } = $props();
</script>

<section class="banner container">
  <div class="banner-card">
    <div class="text">
      <p class="heading-md secondary">{question}</p>
      <p class="heading-md primary">{answer}</p>
    </div>
    <a href={ctaHref} class="button body-md">{ctaText}</a>
  </div>
</section>

<style>
  .banner {
    background: var(--surface-background-primary);
    padding-top: var(--spacing-module-padding-md);
    padding-bottom: var(--spacing-module-padding-md);
  }
  .banner-card {
    display: flex;
    flex-direction: column;
    gap: var(--spacing-gap-xxxl);
    padding: var(--spacing-padding-md);
    background: var(--surface-background-tertiary);
    border-radius: var(--radius-sm);
    width: 100%;
  }
  .text { display: flex; flex-direction: column; }
  .secondary { color: var(--text-default-secondary); }
  .primary { color: var(--text-default-primary); }
  .button {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    height: 40px;
    padding: 0 var(--spacing-gap-lg);
    background: var(--surface-button-primary-default);
    color: var(--text-invert-primary);
    border-radius: var(--radius-sm);
    white-space: nowrap;
    align-self: flex-start;
    transition: background 0.15s ease;
  }
  .button:hover { background: var(--surface-button-primary-hover); }
</style>
