<script>
  import 'minireset.css';
  import '@openfonts/ibm-plex-sans_latin';
  import '@openfonts/ibm-plex-mono_latin';

  import Text from './Text.svelte';
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

  header {
    position: absolute;

    padding: 0.25rem;
  }
</style>

<header>
  <Text>wtform.at</Text>
  <Text>by @timonweber</Text>
</header>

<RecursiveLayout column payload={paperSizes.a.slice(1)} />
<Paper {...paperSizes.a[0]} />
