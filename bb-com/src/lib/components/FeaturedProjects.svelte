<script lang="ts">
  interface Asset {
    url: string;
    alt?: string;
    width?: 'small' | 'large';
  }

  interface Project {
    name: string;
    assets: Asset[];
  }

  let { projects = [
    {
      name: 'Sierra',
      assets: [
        { url: 'https://www.figma.com/api/mcp/asset/9601e3ab-2abc-4439-90d9-29b03ddd19cf', alt: 'Sierra project', width: 'small' as const },
        { url: '', alt: 'Sierra main', width: 'large' as const },
        { url: '', alt: 'Sierra detail', width: 'small' as const }
      ]
    }
  ] }: { projects?: Project[] } = $props();
</script>

<section class="featured-projects container">
  <div class="projects">
    {#each projects as project}
      <div class="project-row">
        <div class="project-info">
          <span class="project-name body-md">{project.name}</span>
        </div>
        <div class="assets">
          {#each project.assets as asset}
            <div class="asset asset--{asset.width ?? 'small'}">
              {#if asset.url}
                <img src={asset.url} alt={asset.alt ?? ''} class="asset-img" />
              {:else}
                <div class="asset-placeholder" aria-hidden="true"></div>
              {/if}
            </div>
          {/each}
        </div>
      </div>
    {/each}
  </div>
</section>

<style>
  .featured-projects {
    background: var(--surface-background-primary);
    padding-top: var(--spacing-module-padding-md);
    padding-bottom: var(--spacing-module-padding-md);
  }
  .projects {
    display: flex;
    flex-direction: column;
    gap: var(--spacing-gap-xxxl);
    width: 100%;
  }
  .project-row {
    display: flex;
    flex-direction: column;
    gap: var(--spacing-gap-lg);
    isolation: isolate;
  }
  .project-info { position: relative; z-index: 2; }
  .project-name { color: var(--text-default-primary); }
  .assets {
    display: flex;
    gap: var(--spacing-gap-sm);
    align-items: center;
    position: relative;
    z-index: 1;
    width: 100%;
  }
  .asset {
    position: relative;
    border-radius: var(--radius-sm);
    overflow: hidden;
    flex-shrink: 0;
    height: 462px;
  }
  .asset--small { width: 346px; }
  .asset--large { flex: 1; min-width: 0; }
  .asset-img,
  .asset-placeholder {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
  .asset-placeholder { background: var(--colour-grey-200); }
  @media (max-width: 744px) {
    .assets { flex-direction: column; }
    .asset, .asset--small, .asset--large {
      width: 100%;
      height: 280px;
      flex-shrink: 1;
    }
  }
</style>
