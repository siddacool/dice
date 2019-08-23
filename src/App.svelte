<script>
  import { Router, Route } from 'svero';
  import Index from './pages/Index.svelte';
  import ThreeD from './pages/ThreeD.svelte';
</script>

<style>
  :global(body) {
    margin: 0;
    padding: 0;
    font-family: 'Nunito Sans', sans-serif;
  }

  :global(*) { box-sizing: border-box; }

  :global(p) {
    margin: 0;
    padding: 0;
  }
</style>

<div class="wrapper">
  <Router>
    <Route path="/" exact component={Index} />
    <Route path="/3d" component={ThreeD} />
  </Router>
</div>
