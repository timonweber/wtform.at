<script>
  import Paper from './Paper.svelte';
  import ResponsiveDisplay from './ResponsiveDisplay.svelte';

  export let column = false;
  export let index = 1;
  export let payload = [];

  let nextIndex = index + 1;
  let nextPayload = [...payload.slice(1)];
  let paperSize = payload[0];
</script>

<style>
  section {
    display: flex;

    width: 100%;
    height: 100%;
  }

  section.column {
    flex-direction: column;
  }

  div {
    flex-basis: 50%;
  }
</style>

<section class:column>
  <div>
    {#if nextPayload.length}
      <svelte:self column={!column} index={nextIndex} payload={nextPayload} />
    {/if}
  </div>

  <div>
    <ResponsiveDisplay {index}>
      <Paper
        orientation={column ? 'landscape' : 'portrait'}
        {index}
        {...paperSize} />
    </ResponsiveDisplay>
  </div>
</section>
