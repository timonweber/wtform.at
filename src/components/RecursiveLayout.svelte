<script>
  import Paper from './Paper.svelte';

  export let column = false;
  export let payload = [];

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
    {#if nextPayload.length}
      <svelte:self column={!column} payload={nextPayload}>
        <slot />
      </svelte:self>
    {:else}
      <slot />
    {/if}
  </div>

  <div class="child">
    <Paper orientation={column ? 'landscape' : 'portrait'} {...paperSize} />
  </div>
</section>
