<script lang="ts">
  const logoUrl = 'https://www.figma.com/api/mcp/asset/59452191-9bd8-4780-ad8f-791f40268f87';

  const contactItems = [
    { label: 'General', href: 'mailto:hello@bakkenbaeck.com', text: 'hello@bakkenbaeck.com' },
    { label: 'Press', href: 'mailto:press@bakkenbaeck.com', text: 'press@bakkenbaeck.com' },
    { label: 'Careers', href: '/careers', text: 'Open positions' },
  ];

  const locations = [
    {
      city: 'OSLO',
      lines: ['Trondheimsveien 135', '0570 Oslo', 'Norway']
    },
    {
      city: 'BONN',
      lines: ['Fürstenstrasse 2–4', '53111 Bonn', 'Germany']
    },
    {
      city: 'AMSTERDAM',
      lines: ['Van Diemenstraat 38', '1013NH Amsterdam', 'The Netherlands']
    },
    {
      city: 'LONDON',
      lines: ['23 Englefield Rd', 'London N1 4JX', 'United Kingdom']
    },
    {
      city: 'BARCELONA',
      lines: ['C. De Pamplona 59', '08005 Barcelona', 'Spain']
    },
  ];

  const bottomLinks = [
    { label: 'A–Z', href: '/a-z' },
    { label: 'Team', href: '/team' },
    { label: 'Tech Blog', href: '/tech-blog' },
    { label: 'X', href: 'https://x.com/bakkenbaeck' },
    { label: 'Instagram', href: 'https://instagram.com/bakkenbaeck' },
    { label: 'Github', href: 'https://github.com/bakkenbaeck' },
    { label: 'Linkedin', href: 'https://linkedin.com/company/bakken-baeck' },
    { label: 'Privacy', href: '/privacy' },
  ];
</script>

<footer class="footer container">
  <a href="/" class="footer-logo">
    <img src={logoUrl} alt="Bakken & Bæck" width="39" height="18" />
  </a>

  <div class="middle">
    <div class="contact">
      {#each contactItems as item}
        <div class="footer-item">
          <span class="footer-label body-md">{item.label}</span>
          <a href={item.href} class="footer-link body-md">{item.text}</a>
        </div>
      {/each}
    </div>

    <div class="locations">
      {#each locations as loc}
        <div class="location">
          <p class="body-md location-text">({loc.city})</p>
          {#each loc.lines as line}
            <p class="body-md location-text">{line}</p>
          {/each}
        </div>
      {/each}
    </div>
  </div>

  <div class="bottom">
    <span class="copyright body-md">© 2010–2024 Bakken &amp; Baeck</span>
    <div class="bottom-links">
      {#each bottomLinks as link}
        <a href={link.href} class="bottom-link body-md">{link.label}</a>
      {/each}
    </div>
  </div>
</footer>

<style>
  .footer {
    background: var(--surface-background-primary);
    display: flex;
    flex-direction: column;
    gap: var(--spacing-gap-xxxl);
    padding-top: var(--spacing-module-padding-md);
    padding-bottom: var(--grid-margin);
  }

  .footer-logo img {
    display: block;
  }

  .middle {
    display: flex;
    gap: var(--grid-gutter);
    align-items: flex-start;
    width: 100%;
  }

  .contact {
    display: flex;
    flex-direction: column;
    gap: var(--spacing-gap-lg);
    width: 464px;
    flex-shrink: 0;
  }

  .footer-item {
    display: flex;
    flex-direction: column;
  }

  .footer-label {
    color: var(--text-default-secondary);
  }

  .footer-link {
    color: var(--text-default-primary);
    transition: opacity 0.15s ease;
  }

  .footer-link:hover {
    opacity: 0.6;
  }

  .locations {
    display: flex;
    flex-wrap: wrap;
    gap: 32px var(--grid-gutter);
    flex: 1;
  }

  .location {
    display: flex;
    flex-direction: column;
    width: 228px;
  }

  .location-text {
    color: var(--text-default-primary);
    white-space: pre;
  }

  .bottom {
    display: flex;
    align-items: center;
    gap: var(--grid-gutter);
    width: 100%;
  }

  .copyright {
    color: var(--text-default-primary);
    width: 464px;
    flex-shrink: 0;
  }

  .bottom-links {
    display: flex;
    gap: var(--spacing-gap-xxl);
    align-items: center;
    flex: 1;
    flex-wrap: wrap;
  }

  .bottom-link {
    color: var(--text-default-primary);
    white-space: nowrap;
    transition: opacity 0.15s ease;
  }

  .bottom-link:hover {
    opacity: 0.6;
  }

  @media (max-width: 744px) {
    .middle {
      flex-direction: column;
    }
    .contact {
      width: 100%;
    }
    .bottom {
      flex-direction: column;
      align-items: flex-start;
    }
    .copyright {
      width: 100%;
    }
    .bottom-links {
      flex-wrap: wrap;
    }
  }
</style>
