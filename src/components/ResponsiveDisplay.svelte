<script>
  export let index;
</script>

<style>
  @media (max-width: 600px) {
    .level-4 {
      display: none;
    }
  }

  @media (max-width: 600px) {
    .level-5 {
      display: none;
    }
  }

  @media (max-width: 1200px) {
    .level-6 {
      display: none;
    }
  }
</style>

<div class="level-{index}">
  <slot />
</div>
