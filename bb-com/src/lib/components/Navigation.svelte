<script lang="ts">
  const logoUrl = 'https://www.figma.com/api/mcp/asset/938b5f3e-95ea-46a4-9608-55a30d1f508c';

  const navItems = [
    { label: 'Work', href: '/work' },
    { label: 'About', href: '/about' },
    { label: 'Team', href: '/team' },
    { label: 'Journal', href: '/journal' },
    { label: 'Clients', href: '/clients' },
  ];
</script>

<nav class="navigation container">
  <div class="nav-inner">
    <div class="main-nav">
      <a href="/" class="logo">
        <img src={logoUrl} alt="Bakken & Bæck" width="39" height="18" />
      </a>
      <div class="nav-items">
        {#each navItems as item}
          <a href={item.href} class="nav-link body-md">{item.label}</a>
        {/each}
      </div>
    </div>
    <a href="/contact" class="cta-button body-md">Get in touch</a>
  </div>
</nav>

<style>
  .navigation {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding-top: var(--grid-margin);
    padding-bottom: var(--grid-margin);
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    z-index: 100;
  }

  .nav-inner {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
  }

  .main-nav {
    display: flex;
    align-items: center;
    gap: var(--spacing-gap-lg);
    background: var(--surface-background-blur);
    backdrop-filter: blur(20px);
    -webkit-backdrop-filter: blur(20px);
    border-radius: var(--radius-sm);
    padding: 0 var(--spacing-padding-md);
    height: 40px;
  }

  .logo img {
    display: block;
    width: 39px;
    height: 18px;
  }

  .nav-items {
    display: flex;
    gap: var(--spacing-gap-lg);
    align-items: center;
  }

  .nav-link {
    color: var(--text-default-primary);
    white-space: nowrap;
    transition: opacity 0.15s ease;
  }

  .nav-link:hover {
    opacity: 0.6;
  }

  .cta-button {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 40px;
    padding: 0 var(--spacing-gap-lg);
    background: var(--surface-button-primary-default);
    color: var(--text-invert-primary);
    border-radius: var(--radius-sm);
    white-space: nowrap;
    transition: background 0.15s ease;
  }

  .cta-button:hover {
    background: var(--surface-button-primary-hover);
  }
</style>
