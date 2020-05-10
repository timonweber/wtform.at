<script>
  export let spacing = false;
</script>

<style>
  div {
    font-family: 'IBM Plex Mono';
    font-size: 0.875rem;
    line-height: 1rem;
  }

  .spacing {
    margin-bottom: 1rem;
  }
</style>

<div class:spacing>
  <slot />
</div>
