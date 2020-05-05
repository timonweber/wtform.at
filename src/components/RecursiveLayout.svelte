<script>
  import Paper from './Paper.svelte';

  export let column = false;
  export let index = 1;
  export let payload = [];

  let nextIndex = index + 1;
  let nextPayload = [...payload.slice(1)];
  let paperSize = payload[0];
</script>

<style>
  .root {
    display: flex;

    width: 100%;
    height: 100%;
  }

  .root.column {
    flex-direction: column;
  }

  .child {
    flex-basis: 50%;
  }
</style>

<section class="root" class:column>
  <div class="child">
    {#if index < 6}
      <svelte:self column={!column} index={nextIndex} payload={nextPayload}>
        <slot />
      </svelte:self>
    {:else}
      <slot />
    {/if}
  </div>

  <div class="child">
    <Paper
      orientation={column ? 'landscape' : 'portrait'}
      {index}
      {...paperSize} />
  </div>
</section>
