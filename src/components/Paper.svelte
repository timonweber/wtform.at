<script>
  import Title from './Title.svelte';
  import Text from './Text.svelte';

  export let orientation = 'portrait';
  export let name, width, height;
</script>

<style>
  article {
    position: relative;

    width: 100%;
    height: 0;

    color: black;
    border: calc(var(--gutter) / 2) solid black;
    background-color: white;
  }

  article.portrait {
    padding-top: calc(141.42135624% - var(--gutter));
  }

  article.landscape {
    padding-top: calc(70.710678119% - var(--gutter));
  }

  div {
    position: absolute;
    top: 50%;
    left: 50%;

    transform: translate(-50%, -50%);
    text-align: center;
    white-space: nowrap;
  }
</style>

<article class={orientation}>
  <div>
    <Title>{name}</Title>
    <Text>{width} &times; {height} mm</Text>
  </div>
</article>
