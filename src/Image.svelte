<script>
    export let src;
    export let retina = true;

    function genNameX(value, n) {
        const divided = value.split(".");
        const nameIdx = divided.length - 2;
        divided[nameIdx] = `${divided[nameIdx]}_${n}x`;
        return divided.join(".");
    }

    function genRetinaSetSrc(src) {
        return `${genNameX(src, 1)} 1x, ${genNameX(src, 2)} 2x`
    }

    $: set = genRetinaSetSrc(src);
</script>

<style>
  picture,
  .image {
    display: block;
  }
</style>

{#if retina}
    <picture>
      <source srcset={set}>
        <img src={src} class="image" alt="image" />
    </picture>
{:else}
    <img src={src} class='image' alt="image" />
{/if}
