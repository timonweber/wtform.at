<script>
  export let active = false;
  export let to = '';
</script>

<style>
  a,
  button {
    padding: 0;

    cursor: pointer;
    text-decoration: none;

    color: inherit;
    border: none;
    outline: none;
    background: none;

    font-family: inherit;
    font-size: inherit;
  }

  .active,
  a:hover,
  button:hover {
    text-decoration: underline;
  }
</style>

{#if to}
  <a class:active href={to}>
    <slot />
  </a>
{:else}
  <button class:active on:click>
    <slot />
  </button>
{/if}
