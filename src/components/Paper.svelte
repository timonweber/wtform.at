<script>
  import ResponsiveDisplay from './ResponsiveDisplay.svelte';
  import Title from './Title.svelte';
  import Text from './Text.svelte';

  export let orientation = 'portrait';
  export let index = 0;
  export let name, width, height;
</script>

<style>
  article {
    position: relative;

    width: 100%;
    height: 0;

    color: black;
    border: 0.25rem solid black;
    background-color: white;
  }

  article.portrait {
    padding-top: calc(141.42135624% - 0.5rem);
  }

  article.landscape {
    padding-top: calc(70.710678119% - 0.5rem);
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
    <ResponsiveDisplay {index}>
      <Title>{name}</Title>
      <Text>{width} &times; {height} mm</Text>
    </ResponsiveDisplay>
  </div>
</article>
