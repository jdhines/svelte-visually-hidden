<script>
  import { onMount } from 'svelte';
  let forceShow = false;

  const handleKeyDown = (ev) => {
    if (ev.key === 'Alt') {
      forceShow = true;
    }
  };
  const handleKeyUp = (ev) => {
    if (ev.key === 'Alt') {
      forceShow = false;
    }
  };
  onMount(() => {
    console.log(`env: ${process.env.NODE_ENV}`);
    if (process.env.NODE_ENV !== 'production') {
      window.addEventListener('keydown', handleKeyDown);
      window.addEventListener('keyup', handleKeyUp);

      return {
        destroy() {
          window.removeEventListener('keydown', handleKeyDown);
          window.removeEventListener('keyup', handleKeyUp);
        },
      };
    }
  });
</script>

<span class={forceShow ? '' : 'hidden'} {...$$props}>
  <slot />
</span>

<style>
  .hidden {
    display: inline-block;
    position: absolute;
    overflow: hidden;
    clip: rect(0 0 0 0);
    height: 1;
    width: 1;
    margin: -1;
    padding: 0;
    border: 0;
  }
</style>
