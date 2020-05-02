<script>
  import 'minireset.css';
  import '@openfonts/ibm-plex-sans_latin';
  import '@openfonts/ibm-plex-mono_latin';

  import RecursiveLayout from './RecursiveLayout.svelte';
  import Paper from './Paper.svelte';

  import paperSizes from '../data/paperSizes.js';
</script>

<style>
  :global(body) {
    padding: 0.25rem;

    color: white;
    background-color: black;
  }
</style>

<RecursiveLayout column payload={paperSizes.a.slice(1)} />
<Paper {...paperSizes.a[0]} />
