<script>
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

  a:hover,
  button:hover {
    text-decoration: underline;
  }
</style>

{#if to}
  <a href={to}>
    <slot />
  </a>
{:else}
  <button on:click>
    <slot />
  </button>
{/if}
