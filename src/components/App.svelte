<script>
  import 'minireset.css';
  import '@openfonts/ibm-plex-sans_latin';
  import '@openfonts/ibm-plex-mono_latin';

  import Paper from './Paper.svelte';
</script>

<style>
  :global(body) {
    padding: 0.25rem;

    color: white;
    background-color: black;
  }
</style>

<Paper name="A0" width={841} height={1189} />
