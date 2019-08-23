<script>
  import { Router, Route } from 'svero';
  import Index from './pages/Index.svelte';
</script>

<style>
  :global(body) {
    margin: 0;
    padding: 0;
  }

  :global(*) { box-sizing: border-box; }

  :global(p) {
    margin: 0;
    padding: 0;
  }
</style>

<div class="wrapper">
  <Index />
</div>
