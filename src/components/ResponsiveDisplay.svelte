<script>
  export let index;
</script>

<style>
  @media (max-width: 600px) {
    .responsive-display-4 {
      display: none;
    }
  }

  @media (max-width: 600px) {
    .responsive-display-5 {
      display: none;
    }
  }

  @media (max-width: 1200px) {
    .responsive-display-6 {
      display: none;
    }
  }
</style>

<div class="responsive-display-{index}">
  <slot />
</div>
