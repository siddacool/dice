<script>
  import { onDestroy } from 'svelte';
  import { status } from '../stores.js';
  export let router = {};

  router.path;
  router.route;
  router.params;

  let theStatus;

  const stat = status.subscribe(val => {
    theStatus = val;
  })

  const chnageStore = () => {
    status.update(n => n = 'bro');
  }

  onDestroy(stat);
</script>

<h1 on:mouseover={chnageStore}>{theStatus}</h1>

<p>This is my router: {router.path}</p>
