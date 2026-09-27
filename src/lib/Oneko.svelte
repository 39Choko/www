<script lang="ts">
  import { onMount } from 'svelte';

  onMount(() => {
    const script = document.createElement('script');
    script.src = '/oneko.js';
    script.dataset.cat = '/oneko.gif';
    script.dataset.persistPosition = 'false';
    script.dataset.anchor = '.card-header';
    document.body.appendChild(script);
  });
</script>
