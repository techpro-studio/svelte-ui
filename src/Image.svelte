<script>
    export let src;
    export let retina = true;
    export let pictureStyle = undefined;
    export let imgStyle = undefined;

    function genNameX(value, n) {
        const divided = value.split(".");
        const nameIdx = divided.length - 2;
        divided[nameIdx] = `${divided[nameIdx]}_${n}x`;
        return divided.join(".");
    }

    function genRetinaSetSrc(src) {
        if (!src){
            return
        }
        return `${src} 1x, ${genNameX(src, 2)} 2x`
    }

    $: set = genRetinaSetSrc(src);

</script>

<style>
  picture,
  .image {
    display: block;
  }
</style>

{#if src}
    {#if retina}
        <picture style={pictureStyle} >
          <source srcset={set}>
            <img src={src} style={imgStyle} class="image" alt="image" />
        </picture>
    {:else}
        <img src={src} class='image' alt="image" />
    {/if}
{/if}
