<script>
  import Title from './Title.svelte';
  import Text from './Text.svelte';

  export let orientation = 'portrait';
  export let name, width, height;
</script>

<style>
  .root {
    position: relative;

    width: 100%;
    height: 0;

    color: black;
    border: 0.25rem solid black;
    background-color: white;
  }

  .root.portrait {
    padding-top: calc(141.42135624% - 0.5rem);
  }

  .root.landscape {
    padding-top: calc(70.710678119% - 0.5rem);
  }

  .content {
    position: absolute;
    top: 50%;
    left: 50%;

    transform: translate(-50%, -50%);
    text-align: center;
    white-space: nowrap;
  }
</style>

<section class="root {orientation}">
  <div class="content">
    <Title>{name}</Title>
    <Text>{width} &times; {height} mm</Text>
  </div>
</section>
