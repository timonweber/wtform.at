<script>
  export let to;
</script>

<style>
  a {
    text-decoration: none;

    color: inherit;
  }

  a:hover {
    text-decoration: underline;
  }
</style>

<a href={to}>
  <slot />
</a>
