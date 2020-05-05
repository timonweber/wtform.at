<script>
  export let index;
</script>

<style>
  @media (max-width: 600px) {
    .level-4 {
      display: none;
    }

    .level-5 {
      display: none;
    }
  }

  @media (max-width: 1200px) {
    .level-6 {
      display: none;
    }

    .level-7 {
      display: none;
    }
  }

  @media (max-width: 2400px) {
    .level-8 {
      display: none;
    }

    .level-9 {
      display: none;
    }
  }
</style>

<div class="level-{index}">
  <slot />
</div>
