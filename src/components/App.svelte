<script>
  import 'minireset.css';
  import '@openfonts/ibm-plex-sans_latin';
  import '@openfonts/ibm-plex-mono_latin';

  import Text from './Text.svelte';
  import Link from './Link.svelte';
  import RecursiveLayout from './RecursiveLayout.svelte';
  import Paper from './Paper.svelte';

  import paperSizesData from '../data/paperSizes.js';

  let series = 'a';
  $: paperSizes = paperSizesData[series];

  const setSeries = key => {
    series = key;
  };
</script>

<style>
  :global(:root) {
    --gutter: 0.72rem;
  }

  :global(body) {
    padding: calc(var(--gutter) / 2);

    color: white;
    background-color: black;
  }

  header {
    position: absolute;

    padding: calc(var(--gutter) / 2);
  }
</style>

<header>
  <Text spacing>
    <h1>wtform.at</h1>
    by
    <Link to="https://twitter.com/timonweber">@timonweber</Link>
  </Text>

  <Text>
    Series:
    {#each Object.keys(paperSizesData) as seriesKey}
      <Link active={seriesKey === series} on:click={() => setSeries(seriesKey)}>
        {seriesKey.toUpperCase()}
      </Link>
      {' '}
    {/each}
  </Text>
</header>

<RecursiveLayout column payload={paperSizes.slice(1)} />
<Paper {...paperSizes[0]} />
