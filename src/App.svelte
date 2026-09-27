<script lang="ts">
  import About    from './lib/About.svelte';
  import Projects from './lib/Projects.svelte';
  import Contact  from './lib/Contact.svelte';
  import Oneko    from './lib/Oneko.svelte';

  type Tab = 'about' | 'projects' | 'contact';

  const tabs: Tab[] = ['about', 'projects', 'contact'];
  let active = $state<Tab>('about');
</script>

<div class="card">
  <header class="card-header">
    <span class="title">{active}</span>
    <nav class="nav-tabs">
      {#each tabs as tab}
        <a
          href="#{tab}"
          class:active={active === tab}
          onclick={(e) => { e.preventDefault(); active = tab; }}
        >{tab}</a>
      {/each}
    </nav>
  </header>

  <main class="card-body">
    {#if active === 'about'}
      <aside class="sidebar">
        <img src="/mafuyu.webp" alt="avatar" />
        <p class="caption">choko — they/them</p>
      </aside>
    {/if}

    {@render tabContent()}
  </main>
</div>

{#snippet tabContent()}
  {#if active === 'about'}
    <About />
  {:else if active === 'projects'}
    <Projects />
  {:else if active === 'contact'}
    <Contact />
  {/if}
{/snippet}

<Oneko />

<style>
  :global(body) {
    background-color: #232333;
    color: #e0e0e0;
    font-family: ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont,
      'Segoe UI', Roboto, sans-serif;
    min-height: 100vh;
    display: grid;
    place-items: center;
    padding: 1rem;
  }

  .card {
    width: 100%;
    max-width: 620px;
    border: 1px solid #1a1a1a;
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.4);
  }

  .card-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: #232333;
    border-bottom: 1px solid #1a1a1a;
  }

  .title {
    font-weight: 700;
    padding: 8px 14px;
    font-size: 0.95rem;
  }

  .nav-tabs {
    display: flex;
  }

  .nav-tabs a {
    color: #a8a29e;
    text-decoration: none;
    padding: 8px 12px;
    font-size: 0.85rem;
    border-left: 1px solid #1d1d26;
    transition: background 0.15s, color 0.15s;
  }

  .nav-tabs a:hover,
  .nav-tabs a.active {
    color: #ffffff;
    background: #343449;
  }

  .card-body {
    display: flex;
    gap: 1.25rem;
    padding: 1.25rem;
  }

  .sidebar {
    flex-shrink: 0;
    width: 130px;
    text-align: center;
  }

  .sidebar img {
    width: 100%;
    height: 130px;
    object-fit: cover;
    display: block;
    border: 1px solid #242220;
  }

  .sidebar .caption {
    font-size: 0.75rem;
    color: #a8a29e;
    margin-top: 6px;
  }

  :global(.content) {
    font-size: 0.85rem;
    line-height: 1.6;
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
  }

  :global(.content a) {
    color: #dfd8c8;
    text-decoration: underline;
    text-underline-offset: 2px;
  }

  :global(.content a:hover) {
    color: #ffffff;
  }

  @media (max-width: 520px) {
    .card-body {
      flex-direction: column;
      align-items: center;
    }
    .sidebar {
      width: 100px;
    }
    .sidebar img {
      height: 100px;
    }
  }
</style>
