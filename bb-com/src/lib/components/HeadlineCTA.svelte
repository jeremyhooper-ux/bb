<script lang="ts">
  let {
    label = 'Capabilities.',
    body = 'Strategy, design, and code — all under one roof',
    ctaText = 'Practice',
    ctaHref = '/practice'
  }: {
    label?: string;
    body?: string;
    ctaText?: string;
    ctaHref?: string;
  } = $props();
</script>

<section class="headline-cta container">
  <div class="inner">
    <p class="heading-md copy">
      <span class="secondary">{label}</span> {body}
    </p>
    <a href={ctaHref} class="button body-md">{ctaText}</a>
  </div>
</section>

<style>
  .headline-cta {
    background: var(--surface-background-primary);
    padding-top: var(--spacing-module-padding-md);
    padding-bottom: var(--spacing-module-padding-md);
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .inner {
    display: flex;
    flex-direction: column;
    gap: var(--spacing-gap-lg);
    width: 464px;
    max-width: 100%;
  }
  .copy { color: var(--text-default-primary); }
  .secondary { color: var(--text-default-secondary); }
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
