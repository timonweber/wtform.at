<script>
  import 'minireset.css';
  import '@openfonts/ibm-plex-sans_latin';
  import '@openfonts/ibm-plex-mono_latin';

  import Text from './Text.svelte';
  import Link from './Link.svelte';
  import RecursiveLayout from './RecursiveLayout.svelte';
  import Paper from './Paper.svelte';

  import paperSizes from '../data/paperSizes.js';
</script>

<style>
  :global(:root) {
    --gutter: 0.48rem;
  }

  :global(body) {
    padding: var(--gutter);

    color: white;
    background-color: black;
  }

  header {
    position: absolute;

    padding: var(--gutter);
  }
</style>

<header>
  <Text>wtform.at</Text>
  <Text>
    by
    <Link to="https://twitter.com/timonweber">@timonweber</Link>
  </Text>
</header>

<RecursiveLayout column payload={paperSizes.a.slice(1)} />
<Paper {...paperSizes.a[0]} />
